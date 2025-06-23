---
title: doPlugins
description: 在編譯點擊並傳送至 Adobe 之前設定邏輯。
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 63%

---

# doPlugins

`doPlugins` 變數會成為「最後呼叫」，負責設定實施中的值。這是呼叫[外掛程式方法](../plugins/impl-plugins.md)並在傳送影像要求之前設定任何所需變數的理想位置。 如果啟用 [`usePlugins`](../config-vars/useplugins.md)，它會在任何類型的影像要求編譯並傳送至 Adobe 之前自動執行，包括：

* 所有頁面瀏覽 ([`t()`](t-method.md)) 呼叫
* 所有連結追蹤 ([`tl()`](tl-method.md)) 呼叫，包括自動下載連結和退出連結

使用 `doPlugins` 變數來呼叫外掛程式程式碼，並在影像要求編譯並傳送至 Adobe 之前設定最終變數值。

## 使用Web SDK擴充功能在Before Event傳送回呼代碼前使用

網頁SDK使用具有類似功能的`onBeforeEventSend`，而非`doPlugins`。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL Adobe Experience Platform Web SDK]底下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
1. 在[!UICONTROL 資料彙集]下，按一下&#x200B;**[!UICONTROL 在事件傳送回撥代碼前編輯]**&#x200B;按鈕。
1. 將所需的程式碼放入編輯器中。

## 使用`onBeforeEventSend`手動實作Web SDK

網頁SDK使用具有類似功能的`onBeforeEventSend`，而非`doPlugins`。 如需詳細資訊，請參閱Web SDK檔案中的[全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hant#modifying-events-globally)。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## 使用Adobe Analytics擴充功能的外掛程式

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和自訂程式碼中的 s.doPlugins

將變數 `s.doPlugins` 設為包含所需程式碼的函數。當您進行追蹤呼叫時，函數會自動執行。

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
> 實施作業中的 `doPlugins` 函數只需要設為變數一次。如果您設定 `doPlugins` 變數多次，只需要使用最新的程式碼就可以了。

## 範例

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>舊版 AppMeasurement 的 `doPlugins()` 程式碼稍有不同。Adobe 建議您使用上述格式作為最佳做法。

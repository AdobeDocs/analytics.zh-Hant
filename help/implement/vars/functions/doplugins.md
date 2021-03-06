---
title: doPlugins
description: 在編譯點擊並傳送至 Adobe 之前設定邏輯。
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 57%

---

# doPlugins

`doPlugins` 變數會成為「最後呼叫」，負責設定實施中的值。如果啟用 [`usePlugins`](../config-vars/useplugins.md)，它會在任何類型的影像要求編譯並傳送至 Adobe 之前自動執行，包括：

* 所有頁面瀏覽 ([`t()`](t-method.md)) 呼叫
* 所有連結追蹤 ([`tl()`](tl-method.md)) 呼叫，包括自動下載連結和退出連結

使用 `doPlugins` 變數來呼叫外掛程式程式碼，並在影像要求編譯並傳送至 Adobe 之前設定最終變數值。

## 使用Web SDK擴展在事件之前發送回調代碼

而不是 `doPlugins`,Web SDK使用 `onBeforeEventSend` 功能相似。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 擴展] ，然後按一下 **[!UICONTROL 配置]** 按鈕 [!UICONTROL Adobe Experience PlatformWeb SDK]。
1. 下 [!UICONTROL 資料收集]，按一下 **[!UICONTROL 在事件發送回調代碼之前編輯]** 按鈕
1. 將所需代碼放入編輯器中。

## 使用 `onBeforeEventSend` 手動實施Web SDK

而不是 `doPlugins`,Web SDK使用 `onBeforeEventSend` 功能相似。 請參閱 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 的子菜單。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## 使用Adobe Analytics擴展插件

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

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

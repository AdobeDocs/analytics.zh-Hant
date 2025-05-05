---
title: abort
description: abort 變數是布林值，可防止將點擊傳送至 Adobe 資料收集伺服器。
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 39%

---

# abort

`abort`變數是布林值，可防止將下一個追蹤呼叫傳送到Adobe。 Web SDK中存在類似的功能，可讓您在傳送XDM事件之前傳回`false`。

## 取消使用Web SDK擴充功能傳送事件

在事件傳送回呼程式碼編輯器之前使用On並傳回`false`。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL Adobe Experience Platform Web SDK]底下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
1. 在[!UICONTROL 資料彙集]下，按一下&#x200B;**[!UICONTROL 在事件傳送回撥代碼前編輯]**&#x200B;按鈕。
1. 在程式碼編輯器中，將下列程式碼置於您想要中止傳送資料至Edge的任何條件下：

```js
return false;
```

## 取消手動實作Web SDK時傳送事件

使用`onBeforeEventSend`回呼並傳回`false`。 如需詳細資訊，請參閱Web SDK檔案中的[全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## 在Adobe Analytics擴充功能中使用abort變數

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.abort

`s.abort` 變數是布林值。其預設值為 `false`。

* 如果設為 `true`，下個追蹤呼叫 ([`t()`](../functions/t-method.md) 或 [`tl()`](../functions/tl-method.md)) 就不會將任何資料傳送至 Adobe。
* 若設為 `false` 或未定義，此變數就不會執行任何動作。

```js
s.abort = true;
```

>[!NOTE]
>
>`abort` 變數會在每個追蹤呼叫後重設為 `false`。若要中止相同頁面上的後續追蹤呼叫，請再次將`abort`設為`true`。

`abort`變數可在[`doPlugins()`](../functions/doplugins.md)函式中設定，該函式是將影像要求傳送至Adobe之前執行的最後一個函式。 此範例的運作方式與使用Web SDK的`onBeforeEventSend`回呼類似。

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

您可以集中邏輯，用於識別不想追蹤的活動，例如自訂連結或顯示廣告中的外部連結。

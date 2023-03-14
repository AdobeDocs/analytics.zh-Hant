---
title: registerPreTrackCallback
description: 將點擊傳送至 Adobe 前建立回呼函數。
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 61%

---

# registerPreTrackCallback

`registerPreTrackCallback` 變數可讓您的組織在影像要求 URL 編譯完成但尚未傳送時，連結 JavaScript 函數。您可以使用此變數將 AppMeasurement 收集的資料傳送至合作夥伴或內部基礎架構。

>[!WARNING]
>
>請勿在 [`registerPostTrackCallback`](registerposttrackcallback.md) 變數內呼叫 [`t()`](t-method.md) 或 [`tl()`](tl-method.md) 之類的任何追蹤呼叫。 此變數中的追蹤函數會導致影像要求發生無限循環！

每次呼叫 `registerPreTrackCallback` 變數時，您都可以連結該函數，以便在影像要求編譯完成時執行。請避免在同一個頁面載入中多次註冊相同的函數。

>[!NOTE]
>
>對於在 `registerPreTrackCallback` 和 `registerPostTrackCallback` 之間引發的函數，我們不能保證引發的時間和順序。 請避免這兩個函數之間有相依性。

## 使用Web SDK擴充功能預先追蹤回呼

Web SDK無法在資料編譯後，但在將其傳送至Adobe之前連結函式。 不過，您可以使用 `onBeforeEventSend` 登錄函式以在發送資料之前執行。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往 [!UICONTROL 擴充功能] ，然後按一下 **[!UICONTROL 設定]** 按鈕 [!UICONTROL Adobe Experience Platform Web SDK].
1. 在 [!UICONTROL 資料收集]，按一下 **[!UICONTROL 在事件傳送回呼程式碼之前編輯]** 按鈕。
1. 將所需的程式碼放入編輯器中。

## 手動實作Web SDK的預先追蹤回呼

Web SDK無法在資料編譯後，但在將其傳送至Adobe之前連結函式。 不過，您可以使用 `onBeforeEventSend` 在資料傳送前註冊要執行的函式，類似於 `doPlugins`. 請參閱 [全域修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 如需詳細資訊，請參閱網頁SDK檔案。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## 使用Adobe Analytics擴充功能預先追蹤回呼

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.registerPreTrackCallback

`s.registerPreTrackCallback` 是能將函數當作唯一引數的函數。巢狀函數會在影像要求傳送之前執行。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

如果您想在程式碼中使用影像要求 URL，請在巢狀函數內參考 `requestUrl` 字串引數。您可以解析 `requestUrl` 變數來滿足所需用途；調整此變數不會影響資料彙集。

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

您可以在 `s.registerPreTrackCallback` 函數中加入其他引數，這些引數可用於巢狀函數：

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>設定頁面變數或變更此函數中的 `requestUrl` 字串&#x200B;**不會**&#x200B;影響此函數呼叫後不久傳送的影像要求。 請改用 [`doPlugins()`](doplugins.md) 變數。

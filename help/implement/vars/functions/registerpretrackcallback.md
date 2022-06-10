---
title: registerPreTrackCallback
description: 將點擊傳送至 Adobe 前建立回呼函數。
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 55%

---

# 註冊PreTrackCallback

`registerPreTrackCallback` 變數可讓您的組織在影像要求 URL 編譯完成但尚未傳送時，連結 JavaScript 函數。您可以使用此變數將 AppMeasurement 收集的資料傳送至合作夥伴或內部基礎架構。

>[!WARNING]
>
>請勿在 [`registerPostTrackCallback`](registerposttrackcallback.md) 變數內呼叫 [`t()`](t-method.md) 或 [`tl()`](tl-method.md) 之類的任何追蹤呼叫。 此變數中的追蹤函數會導致影像要求發生無限循環！

每次呼叫 `registerPreTrackCallback` 變數時，您都可以連結該函數，以便在影像要求編譯完成時執行。請避免在同一個頁面載入中多次註冊相同的函數。

>[!NOTE]
>
>對於在 `registerPreTrackCallback` 和 `registerPostTrackCallback` 之間引發的函數，我們不能保證引發的時間和順序。 請避免這兩個函數之間有相依性。

## 使用Web SDK擴展進行預跟蹤回調

Web SDK在編譯資料後但在將其發送到Adobe之前無法掛接函式。 但是，您可以 `onBeforeEventSend` 在發送資料之前註冊要執行的函式。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 擴展] ，然後按一下 **[!UICONTROL 配置]** 按鈕 [!UICONTROL Adobe Experience PlatformWeb SDK]。
1. 下 [!UICONTROL 資料收集]，按一下 **[!UICONTROL 在事件發送回調代碼之前編輯]** 按鈕
1. 將所需代碼放入編輯器中。

## 手動實現Web SDK的預跟蹤回調

Web SDK在編譯資料後但在將其發送到Adobe之前無法掛接函式。 但是，您可以 `onBeforeEventSend` 在資料發送前註冊要執行的函式，類似於 `doPlugins`。 請參閱 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 的子菜單。

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## 使用Adobe Analytics分機的預跟蹤回調

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement中的s.registerPreTrackCallback和Analytics擴展自定義代碼編輯器

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

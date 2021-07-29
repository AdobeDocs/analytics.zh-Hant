---
title: registerPreTrackCallback
description: 將點擊傳送至 Adobe 前建立回呼函數。
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 90%

---

# registerPreTrackCallback

`registerPreTrackCallback` 變數可讓您的組織在影像要求 URL 編譯完成但尚未傳送時，連結 JavaScript 函數。您可以使用此變數將 AppMeasurement 收集的資料傳送至合作夥伴或內部基礎架構。

>[!IMPORTANT]
>
> 請勿在 [`t()`](t-method.md) 變數內呼叫 [`tl()`](tl-method.md) 或 [`registerPostTrackCallback`](registerposttrackcallback.md) 之類的追蹤呼叫。此變數中的追蹤函數會導致影像要求發生無限循環！

每次呼叫 `registerPreTrackCallback` 變數時，您都可以連結該函數，以便在影像要求編譯完成時執行。請避免在同一個頁面載入中多次註冊相同的函數。

>[!NOTE]
>
> 對於在 `registerPreTrackCallback` 和 `registerPostTrackCallback` 之間引發的函數，我們不能保證引發的時間和順序。請避免這兩個函數之間的依賴關係。

## 在Adobe Experience Platform中使用標籤註冊前置追蹤回呼

資料收集UI中沒有專用欄位可使用此變數。 依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 自訂程式碼編輯器中的 s.registerPreTrackCallback

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
> 設定頁面變數或變更此函數中的 `requestUrl` 字串，**不會**&#x200B;影響此函數呼叫後不久傳送的影像要求。請改用 [`doPlugins()`](doplugins.md) 變數。

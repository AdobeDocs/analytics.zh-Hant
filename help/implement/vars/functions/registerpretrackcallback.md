---
title: registerPreTrackCallback
description: 在傳送點擊至Adobe之前建立回呼函式。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# registerPreTrackCallback

此變 `registerPreTrackCallback` 數可讓您的組織在編譯影像請求URL後，但在傳送之前，先勾選JavaScript函式。 您可以使用此變數，將AppMeasurement收集的資料傳送至合作夥伴或內部基礎架構。

> [!IMPORTANT] 請勿呼叫任何追蹤呼叫， [`t()`](t-method.md) 例如 [`tl()`](tl-method.md) 或在變數 [`registerPostTrackCallback`](registerposttrackcallback.md) 內。 此變數中的追蹤函式會造成影像要求的無限回圈！

每次呼叫變數 `registerPreTrackCallback` 時，您都會勾選該函式，以便在每次編譯影像要求URL時執行。 請避免在同一頁面載入中多次註冊相同的函式。

> [!NOTE] 在和之間觸發的函式的時 `registerPreTrackCallback` 間和 `registerPostTrackCallback` 順序不保證。 避免這兩個函式之間的依賴關係。

## 在Adobe Experience Platform Launch中註冊預追蹤回呼

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.registerPreTrackCallback

是 `s.registerPreTrackCallback` 一個函式，它將函式作為其唯一參數。 巢狀函式會在傳送影像要求之前執行。

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

如果您想在程式碼中使用影像要求URL，請參考巢狀函 `requestUrl` 數內的字串引數。 您可以解析變 `requestUrl` 數以供您所需使用；調整此變數不會影響資料收集。

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

您可以在函式中包含其 `s.registerPreTrackCallback` 他引數，這些引數可用於巢狀函式：

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

> [!NOTE] 設定頁面變數或變更 `requestUrl` 此函式中的字串 **不會影響** ，此函式呼叫後不久傳送的影像要求。 請改用 [`doPlugins()`](doplugins.md) 變數。

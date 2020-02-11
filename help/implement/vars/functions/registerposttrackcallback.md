---
title: registerPostTrackCallback
description: 在傳送點擊至Adobe後建立回呼函式。
translation-type: tm+mt
source-git-commit: acfcb1f27650649581875680e7897e5c9813765a

---


# registerPostTrackCallback

此變 `registerPostTrackCallback` 數可讓貴組織在成功將點擊傳送至Adobe後，立即勾選JavaScript函式。 如果追蹤呼叫失敗，此函式將不執行。 您可以使用此變數，將AppMeasurement收集的資料傳送至合作夥伴或內部基礎架構，或清除單頁應用程式中的變數值。

> [!IMPORTANT] 請勿呼叫任何追蹤函式， `t` 例如 `tl` 變數 `registerPostTrackCallback` 內。 此變數中的追蹤函式會造成影像要求的無限回圈！

每次呼叫變數 `registerPostTrackCallback` 時，您都會勾選該函式，以便在成功傳送影像要求後立即執行。 請避免在同一頁面載入中多次註冊相同的函式。

> [!NOTE] 在和之間觸發的函式的時 `registerPreTrackCallback` 間和 `registerPostTrackCallback` 順序不保證。 避免這兩個函式之間的依賴關係。

## 在Adobe Experience Platform Launch中註冊貼文追蹤回呼

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.registerPostTrackCallback

是 `s.registerPostTrackCallback` 一個函式，它將函式作為其唯一參數。 巢狀函式會在傳送影像要求之前執行。

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

如果您想在程式碼中使用影像要求URL，請參考巢狀函 `requestUrl` 數內的字串引數。 您可以解析變 `requestUrl` 數以供您所需使用；調整此變數不會影響資料收集。

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

函式中可包含其他引 `s.registerPostTrackCallback` 數，這些引數可用於嵌套函式：

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## 使用案例範例

在貼文追 `clearVars()` 蹤回呼中註冊函式對單頁應用程式有好處。 每次您成功傳送點擊至Adobe時，函式 `clearVars()` 就會執行。 然後，您的實作可以重新定義變數，而不必擔心值的持續性不正確。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```

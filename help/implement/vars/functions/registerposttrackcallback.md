---
title: registerPostTrackCallback
description: 將點擊傳送至 Adobe 後建立回呼函數。
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 79%

---

# registerPostTrackCallback

`registerPostTrackCallback` 變數可讓貴組織在成功將點擊傳送至 Adobe 後，立即連結 JavaScript 函數。如果追蹤呼叫失敗，此函數將不會執行。您可以使用此變數將 AppMeasurement 收集的資料傳送至合作夥伴或內部基礎架構，或是清除單頁應用程式中的變數值。

>[!WARNING]
>
>請勿在 `registerPostTrackCallback` 變數內呼叫 [`t()`](t-method.md) 或 [`tl()`](tl-method.md) 之類的追蹤呼叫。 此變數中的追蹤函數會導致影像要求發生無限循環！

每次呼叫 `registerPostTrackCallback` 變數時，您都可以連結該函數，以便在成功傳送影像要求後立即執行。請避免在同一個頁面載入中多次註冊相同的函數。

>[!NOTE]
>
>對於在 [`registerPreTrackCallback`](registerpretrackcallback.md) 和 `registerPostTrackCallback` 之間引發的函數，我們不能保證引發的時間和順序。 請避免這兩個函數之間有相依性。

## 使用Web SDK擴充功能進行追蹤後回呼

即將推出!

## 追蹤後回呼手動實作Web SDK

在成功將資料傳送至Adobe後，傳送事件以註冊函式時，您可以使用JavaScript Promise。

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

請參閱 [處理來自事件的回應](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#handling-responses-from-events) 如需詳細資訊，請參閱網頁SDK檔案。

## 使用Adobe Analytics擴充功能註冊追蹤後回呼

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.registerPostTrackCallback

`s.registerPostTrackCallback` 是能將函數當成其唯一引數的函數。 巢狀函數會在成功傳送影像要求之後立即執行。

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

如果您想在程式碼中使用影像要求 URL，請在巢狀函數內參考 `requestUrl` 字串引數。您可以解析 `requestUrl` 變數來滿足所需用途；調整此變數不會影響資料彙集。

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

`s.registerPostTrackCallback` 函數中可包含其他引數，這些引數可用於巢狀函數：

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## 使用案例範例

在後續追蹤回呼中註冊 [`clearVars()`](clearvars.md) 函數對單頁應用程式有好處。當您每次成功將點擊傳送至 Adobe 時，`clearVars()` 函數就會執行。接下來，您的實施便能重新定義變數，不必擔心存留的值不正確。

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```

---
title: 使用 AJAX 進行實作
description: 瞭解如何使用AJAX在網站上實作Adobe Analytics。
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# 使用 AJAX 進行實作

AJAX是使用JavaScript和HTML來清除和產生內容而不載入新頁面的慣例。

Adobe Analytics通常需要重新載入頁面來重設Analytics追蹤物件。 每次導覽至不同的URL時，所有Analytics變數都會重設，並可重新定義。 在您的網站上使用AJAX時，請針對缺少頁面重新整理來調整實作，以確保點擊之間的資料不會不正確地持續存在。

一旦您有了清除變數值的措施，在使用AJAX的網站上實作Adobe Analytics大多與其他實作方法相同。

## 決定互動與點擊類型

由於使用AJAX的頁面通常不會重新載入，所以使用者可以在您的網站上進行多次互動。 實作Adobe Analytics時，請務必區分頁面檢視和連結追蹤呼叫。 針對使用者在您網站上可進行的每次互動，請考慮下列問題：

*當使用者與我的網站互動時，該互動是否會改變頁面上的內容，以符合新頁面的資格？*

* 如果答案是 **是**，請考慮使用頁面檢視追蹤呼叫(`s.t()`)。
* 如果答案為否 ****，請考慮使用連結追蹤呼叫(`s.tl()`)來追蹤互動。

> [!NOTE] 並非所有互動或點按都需要記錄。 請仔細考慮哪些動作最需要追蹤，並據以傳送資料至Adobe。

## 清除每個頁面上的變數

變數值會使用AJAX存留在頁面上，因為頁面不會重新載入。 因此，需要特殊的容許來清除變數值，以免這些值在點擊間不正確地持續存在。 Adobe提供了 [`clearVars`](../vars/functions/clearvars.md) 可輕鬆清除變數值的函式。 請務必在將每個點擊傳送至Adobe之後，以及設定下次點擊的變數值之前，使用此函式。

> [!TIP] 此函 `clearVars()` 數在H代碼中不可用。 如果您尚未升級至AppMeasurement，請將每個Analytics變數值設為空字串。

## 範例

下列範例使用簡單的JavaScript來清除現有的變數值、設定新值，然後傳送影像要求給Adobe:

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

以下範例顯示 JQuery `.ajax` 函數 `done` 回呼中的追蹤呼叫:

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```

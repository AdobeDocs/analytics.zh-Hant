---
title: 使用 AJAX 進行實施
description: 瞭解如何使用 AJAX 在網站上實施 Adobe Analytics。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 使用 AJAX 進行實施

AJAX 是一種作法，使用 JavaScript 和 HTML 來清除和產生內容而不載入新頁面。

Adobe Analytics 通常需要重新載入頁面才能重設 Analytics 追蹤物件。每次導覽至不同的 URL 時，所有 Analytics 變數都會重設且可重新定義。在您的網站上使用 AJAX 時，請針對缺少頁面重新整理來調整實施，以確保點擊之間的資料不會錯誤地持續存在。

只要清除變數值的措施就緒，在使用 AJAX 的網站上實施 Adobe Analytics 大多與其他實施方法相同。

## 決定互動與點擊類型

由於使用 AJAX 的頁面通常不會重新載入，所以使用者可以在您的網站上進行多次互動。實施 Adobe Analytics 時，請務必區分頁面檢視和連結追蹤呼叫。請針對使用者可在您網站上進行的每種互動，考慮下列問題：

*使用者與我的網站互動時，該互動是否會改變頁面上的內容以符合成為新頁面的資格？*

* 如果答案為&#x200B;**是**，請考慮使用頁面檢視追蹤呼叫 (`s.t()`)。
* 如果答案為&#x200B;**否**，請考慮使用連結追蹤呼叫 (`s.tl()`) 來追蹤互動。

>[!NOTE] 並非所有互動或點按都需加以記錄。請仔細考慮哪些動作最需要追蹤，並據此將資料傳送至 Adobe。

## 清除每個頁面上的變數

變數值會持續存在於使用 AJAX 在頁面上，因為頁面不會重新載入。因此，需要進行特殊的調整來清除變數值，以免這些值在點擊間錯誤地持續存在。Adobe 提供的 [`clearVars`](../vars/functions/clearvars.md) 函數可輕鬆清除變數值。將每個點擊傳送至 Adobe 之後，以及設定下次點擊的變數值之前，請務必使用此函數。

>[!TIP] `clearVars()` 函數無法在 H Code 中使用。如果您尚未升級至 AppMeasurement，請將每個 Analytics 變數值設為空字串。

## 範例

下列範例使用簡單的 JavaScript 來清除現有的變數值、設定新值，然後將影像要求傳送至 Adobe：

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

以下範例顯示 JQuery `.ajax` 函數 `done` 回呼中的追蹤呼叫：

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

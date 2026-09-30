---
title: 使用 AJAX 進行實施
description: 瞭解如何使用 AJAX 在網站上實施 Adobe Analytics。
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
role: Developer
autotag-review: '2026-05-22T08:06:40.936Z'
TQID: 'https://experienceleague.adobe.com/M0MNFZRcHpPwxL-ZtTky67DHDr1A0fL-peaGKicXgIM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 100%
---
# 使用 AJAX 進行實施

AJAX 是一種作法，使用 JavaScript 和 HTML 來清除和產生內容而不載入新頁面。

Adobe Analytics 通常需要重新載入頁面才能重設 Analytics 追蹤物件。 每次導覽至不同的 URL 時，所有 Analytics 變數都會重設且可重新定義。 在您的網站上使用 AJAX 時，請針對缺少頁面重新整理來調整實施，以確保點擊之間的資料不會錯誤地持續存在。

一旦您已採取可清除變數值的措施，在使用 AJAX 的網站上實施 Adobe Analytics 大多與其他實施方法相同。

## 決定互動與點擊類型

由於使用 AJAX 的頁面通常不會重新載入，所以使用者可以在您的網站上進行多種互動。 實施 Adobe Analytics 時，請務必區分頁面檢視和連結追蹤調用。 請針對使用者可在您網站上進行的每種互動，考慮下列問題：

*使用者與我的網站互動時，該互動是否會改變頁面上的內容以符合成為新頁面的資格？*

* 如果答案為&#x200B;**是**，請考慮使用頁面檢視追蹤呼叫 (`s.t()`)。
* 如果答案為&#x200B;**否**，請考慮使用連結追蹤呼叫 (`s.tl()`) 來追蹤互動。

>[!NOTE]
>
>並非所有互動或點按都需加以記錄。 請仔細考慮哪些動作最需要追蹤，並據此將資料傳送至 Adobe。

## 清除每個頁面上的變數

由於頁面不會重新載入，因此在使用 AJAX 的頁面上，變數值會持續存在。 因此，需要進行特殊的調整來清除變數值，以免這些值在點擊間錯誤地持續存在。 Adobe 提供的 [`clearVars`](../vars/functions/clearvars.md) 函數可輕鬆清除變數值。 將每個點擊傳送至 Adobe 之後，以及設定下次點擊的變數值之前，請務必使用此函數。

>[!TIP]
>
>`clearVars()` 函數無法在 H Code 中使用。 如果您尚未升級至 AppMeasurement，請將每個 Analytics 變數值設為空字串。

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

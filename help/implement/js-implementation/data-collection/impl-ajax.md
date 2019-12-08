---
description: 使用 AJAX 進行實施的程序，與將程式碼部署在標準 HTML 頁面上完全相同。
keywords: Analytics Implementation
title: 使用 AJAX 進行實作
topic: Developer and implementation
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用 AJAX 進行實作

使用 AJAX 進行實施的程序，與將程式碼部署在標準 HTML 頁面上完全相同。

企業有問題需要解答時，這些需求會受到評估，並指派變數。接著會套用並部署此設計。在經歷實施的初始階段後，您應已熟悉這些概念。

## 設計解決方案 {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

在搭配使用 [!UICONTROL AJAX] 時，差別在於必須先瞭解蒐集的資料須達到怎樣的詳細程度。頁面上的內容變更 (巨集層級) 或追蹤應用程式屬性 (微層級) 的可能性，會決定所應設定的變數以及最適合用來將資料傳送至 Adobe 的方法。

## 部署程式碼 {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

JavaScript 程式碼中有兩個函數可讓您傳送資料。您應遵循幾項需留意的指引，以瞭解應採用哪種方法來傳送資料。若先前曾在相同頁面上提出影像請求，您必須先清除先前設定的變數值。使用 JavaScript 適用的 [!DNL AppMeasurement] 中的 `clearVars()` 函數，或是撰寫簡單的 JavaScript 函數來清除變數 (若您使用的是 H-Code)。為已變更的內容設定適當的值，即 *`pageName`* 變數。設定變數後，請呼叫 *`t()`* 函數。

> [!NOTE]呼叫 `s.t()` 前，您必須先清除 s 物件上不想留存的任何值。如果您使用的是 JavaScript 適用的 [!DNL AppMeasurement]，則可呼叫 `s.clearVars()`。如果您使用 H 程式碼，請撰寫簡單常式來將變數設為空白字串。

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

以下範例顯示 JQuery `.ajax` 函數 `done` 回呼中的追蹤呼叫:

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 
```

若先前曾在相同頁面上提出影像要求，請清除先前設定的變數值。這可以透過下列動作來執行: 

* 撰寫簡單的 JavaScript 函數，以清除 Adobe 變數。
* 設定 *`linkTrackVars`* 和 *`linkTrackEvents`* 變數 (若尚未在 [!DNL s_code.js] 檔案中設定)。

* 為已變更的內容設定適當的值，即 *`pageName`* 變數。
* 設定變數後，請呼叫 *`tl()`* 函數。

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```


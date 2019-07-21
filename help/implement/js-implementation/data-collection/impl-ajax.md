---
description: 使用 AJAX 進行實施的程序，與將程式碼部署在標準 HTML 頁面上完全相同。
keywords: Analytics 實施
seo-description: 使用 AJAX 進行實施的程序，與將程式碼部署在標準 HTML 頁面上完全相同。
seo-title: 使用 AJAX 進行實施
solution: Analytics
title: 使用 AJAX 進行實施
topic: 開發人員和實施
uuid: 9e3477ef-7dea-4c76-ab61-36a188222 be7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用 AJAX 進行實施

使用 AJAX 進行實施的程序，與將程式碼部署在標準 HTML 頁面上完全相同。

企業有問題需要解答時，這些需求會受到評估，並指派變數。接著會套用並部署此設計。在經歷實施的初始階段後，您應已熟悉這些概念。

## 設計解決方案 {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

在搭配使用 [!UICONTROL AJAX] 時，差別在於必須先瞭解蒐集的資料須達到怎樣的詳細程度。頁面上的內容變更 (巨集層級) 或追蹤應用程式屬性 (微層級) 的可能性，會決定所應設定的變數以及最適合用來將資料傳送至 Adobe 的方法。

## 部署程式碼 {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

JavaScript 程式碼中有兩個函數可讓您傳送資料。您應遵循幾項需留意的指引，以瞭解應採用哪種方法來傳送資料。若先前曾在相同頁面上提出影像請求，您必須先清除先前設定的變數值。Use the `clearVars()` funtion in [!DNL AppMeasurement] for JavaScript, or write a simple JavaScript function to clear the variables if you are using H code. Set the values appropriate for the changed content, namely the *`pageName`* variable. After the variables are set call the *`t()`* function.

>[!NOTE]
>
>Before you call `s.t()`, you must clear any values on the s object that you do not want to persist. if you are using [!DNL AppMeasurement] for JavaScript, you can call `s.clearVars()`. 如果您使用 H 程式碼，請撰寫簡單常式來將變數設為空白字串。

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

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
* 設定 *`linkTrackVars`**`linkTrackEvents`* 和變數 [!DNL s_code.js] 。

* Set the values appropriate for the changed content, namely the *`pageName`* variable.
* After the variables are set, call the *`tl()`* function.

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


---
description: JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。
keywords: Analytics Implementation
subtopic: Plug-ins
title: doPlugins 函數
topic: Developer and implementation
uuid: 367d5550-f8e2-477d-8681-18ae9665d699
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# doPlugins 函數

JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。

因此，若您在 `doPlugins` 函數中設定了變數，即可能會覆寫您在 HTML 頁面上設定的變數。唯一不會呼叫 `doPlugins` 函數就是將 *`usePlugins`* 變數設為 `false` 的時候。

**程式碼範例**

`doPlugins` 函數一般被稱為 `s_doPlugins`。但在特定情況下 (通常是單一頁面上可能出現多個版本的 [!DNL Analytics] 程式碼時)，您可以變更 `doPlugins` 函數名稱。如需重新命名標準 `doPlugins` 函數以避免產生衝突，請為 `doPlugins` 指派正確的函數名稱，如下列範例所示。

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**使用 doPlugins**

此函數可讓您輕鬆地為變數指定預設值，或是從網站上任何頁面上的查詢字串參數取用值。使用 `doPlugins` 可能會比在 HTML 頁面上填入值容易，因為只需更新一個檔案即可。JavaScript 檔案的變更不一定都是立即生效的。網站的回訪訪客常會使用快取版本的 JavaScript 檔案。也就是說，檔案的更新最遲在變更完成後的一個月，都還不會套用至所有版本。

下列範例說明應如何使用 `doPlugins` 函數來設定變數的預設值，以及如何從查詢字串獲取值。

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**已安裝的外掛程式**

要確認外掛程式是否包含在您的 JavaScript 檔案中並且可供使用，請查詢 JavaScript 檔案的[!UICONTROL 外掛程式區段]。以下範例說明 `getQueryParam` 函數在[!UICONTROL 外掛程式區段]中會如何呈現。

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ...
// 
```


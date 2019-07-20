---
description: JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。
keywords: Analytics 實施
seo-description: JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。
seo-title: 使用doPlugins函數呼叫外掛程式
solution: Analytics
subtopic: 外掛程式
title: 使用doPlugins函數呼叫外掛程式
topic: 開發人員和實施
uuid: 95dd01de-8136-4ec9-aac9-4a3 d5371 b839
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# 使用doPlugins函數呼叫外掛程式

JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。

Consequently, if you set a variable in the *`doPlugins`* function, you can overwrite a variable you set on the HTML page. *`doPlugins`* 只有 [!UICONTROL 當usePlugins] 變數設為'false'時，才會呼叫函數。

## 程式碼範例 {#section_6940FD16F2E94753A1C39694D0CF5FBA}

The code example below is what the *`doPlugins`* function looks like in your JavaScript file:

JavaScript 適用的 AppMeasurement:

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

H 程式碼:

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

>[!NOTE]
>
>H程式碼及舊版使用不同語法來支援一些非常老舊的瀏覽器(例如IE和5)。

## Renaming the doPlugins Function {#section_70B7D58E057B48058E25907AB3726725}

The *`doPlugins`* function is typically called *`s_doPlugins`*. In certain circumstances, (usually when more than one version of code may appear on a single page) the *`doPlugins`* function name may be changed. If the standard *`doPlugins`* function needs to be renamed to avoid conflicts, ensure that *`doPlugins`* is assigned the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## 使用 doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

*`doPlugins`* 此函數可讓您輕鬆地為變數指定預設值，或從網站任何頁面上 [!UICONTROL 的查詢字串參數] 取用值。Using *`doPlugins`* is often easier than populating the values in the HTML page because only one file must be updated. 請留意，JavaScript 檔案的變更不一定都是立即生效的。網站的回訪訪客常會使用快取版本的 JavaScript 檔案。也就是說，檔案的更新最遲在變更完成後的一個月，都還不會套用至所有訪客。

下列範例說明應如何使用 *`doPlugins`* 函數來設定變數的預設值，以及從查詢字串獲取值。

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
 // if prop1 doesn't have a value, set it to "Default Value" 
 if(!s.prop1) 
s.prop1="Default Value" 
 
 // if campaign doesn't have a value, get cid from the query string 
 if(!s.campaign) 
s.campaign=s.getQueryParam('cid'); 
 
// Note: The code to read query parameters is different for  
// Appmeasurement for JavaScript since a plug-in is not required: 
// s.campaign=s.Util.getQueryParam('cid'); 
} 
```

## 已安裝的外掛程式 {#section_C5494347D85940A78670032199787CD0}

要確認外掛程式是否包含在您的 JavaScript 檔案中並且可供使用，請查看 JavaScript 檔案的[!UICONTROL 外掛程式區段]。下列範例說明 [!UICONTROL getQueryParam] 函數。

```js
/************************** PLUGINS SECTION *************************/ 
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```


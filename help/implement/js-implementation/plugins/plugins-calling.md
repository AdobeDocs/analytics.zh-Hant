---
description: JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。
keywords: Analytics 實作
seo-description: JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。
seo-title: 使用 doPlugins 函數呼叫外掛程式
solution: Analytics
subtopic: 外掛程式
title: 使用 doPlugins 函數呼叫外掛程式
topic: 開發人員和實作
uuid: 95dd01de-8136-4ec9-aac9-4a3d5371b839
translation-type: ht
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# 使用 doPlugins 函數呼叫外掛程式

JavaScript 外掛程式通常被 doPlugins 函數呼叫，該動作會於 t() 函數在貼上程式碼中被呼叫時執行。

因此，若您在 *`doPlugins`* 函數中設定了變數，即可覆寫您在 HTML 頁面上設定的變數。唯一不會呼叫 *`doPlugins`* 函數就是將 [!UICONTROL usePlugins] 變數設為「false」的時候。

## 程式碼範例 {#section_6940FD16F2E94753A1C39694D0CF5FBA}

下列程式碼範例顯示 *`doPlugins`* 函數在 JavaScript 檔案中會如何呈現:

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
>H-Code 及較舊版本使用不同語法來支援某些極舊的瀏覽器 (例如 IE 4 和 5)。

## 重新命名 doPlugins 函數 {#section_70B7D58E057B48058E25907AB3726725}

*`doPlugins`* 函數通常稱為 *`s_doPlugins`*。在特定情況下 (通常是單一頁面上可能出現多個版本的程式碼時)，*`doPlugins`* 函數名稱可能會改變。如需重新命名標準 *`doPlugins`* 函數以避免產生衝突，請確保為 *`doPlugins`* 指派正確的函數名稱，如下列範例所示。

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## 使用 doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

*`doPlugins`* 函數可讓您輕鬆地為變數指定預設值，或是從網站上任何頁面上的[!UICONTROL 查詢字串參數]取用值。使用 *`doPlugins`* 通常會比在 HTML 頁面上填入值來得容易，因為只需更新一個檔案即可。請留意，JavaScript 檔案的變更不一定都是立即生效的。網站的回訪訪客常會使用快取版本的 JavaScript 檔案。也就是說，檔案的更新最遲在變更完成後的一個月，都還不會套用至所有訪客。

下列範例說明應如何使用  *`doPlugins`* 函數來設定變數的預設值，以及從查詢字串獲取值。

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


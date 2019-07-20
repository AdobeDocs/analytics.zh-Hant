---
description: 若在現行頁面 URL 中找到指定的查詢字串參數值，則加以傳回。由於重要資料 (例如促銷活動追蹤程式碼、內部搜尋關鍵字等)都可在頁面上的查詢字串中使用，因此  getQueryParam 有助於將資料擷取至 Analytics 變數中。
keywords: Analytics 實施
seo-description: 若在現行頁面 URL 中找到指定的查詢字串參數值，則加以傳回。由於重要資料 (例如促銷活動追蹤程式碼、內部搜尋關鍵字等)都可在頁面上的查詢字串中使用，因此   getQueryParam 有助於將資料擷取至 Analytics 變數中。
seo-title: getQueryParam
solution: Analytics
subtopic: 外掛程式
title: getQueryParam
topic: 開發人員和實施
uuid: ba202756-c728-4ebc-8fd9-5bc29 a9 f673 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getQueryParam

若在現行頁面 URL 中找到指定的查詢字串參數值，則加以傳回。由於重要資料 (例如促銷活動追蹤程式碼、內部搜尋關鍵字等)都可在頁面上的查詢字串中使用，因此  getQueryParam 有助於將資料擷取至 Analytics 變數中。

>[!IMPORTANT]
>
>此增效模組僅供H程式碼使用。[JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 適用的AppMeasurement可使用 [Util. getQueryParam原生提供此功能](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)。

Once installed in your [!DNL AppMeasurement] for JavaScript code, the plug-in is configured by selecting a [!DNL Analytics] variable to populate using data found in the query string, and specifying which query string values to capture. 外掛程式會偵測指定的查詢字串，若偵測到，即會以其值填入選擇的變數中。若沒有找到該值的查詢字串參數，則會返回空字串。If a query string parameter exists but does not have a value (such as param1 in `?param1&param2=value`), the word *`true`* is returned.

>[!NOTE]
>
>The base code for the plug-in must be installed in your [!DNL AppMeasurement] for JavaScript code before the examples below will work.

If you wanted to use *`s.campaign`* to capture campaign tracking codes available as values of the *`cid`* query parameter, you would enter the following in the *`doPlugins()`* function in your [!DNL AppMeasurement] for JavaScript code:

`s.campaign=s.getQueryParam('cid')`

In this example, if the user arrived at a landing page on your site where the URL was [!DNL https://www.yoursite.com/index.html?cid=123456], then *`s.campaign`* would receive a value of *123456*. 這可以用 [!DNL DigitalPulse] 偵錯器來檢視，其中應會將 *v0=123456* 顯示為影像要求的一部分。

>[!NOTE]
>
>The parameter *`cid`* and others are used here as examples. 您可以將其替換為您的網站上任何現有的查詢字串參數。

此&#x200B;*`getQueryParam`*&#x200B;外掛程式還有兩個引數 (選項) 可用來將資料擷取到 Analytics 變數中: 

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

若 *p* 是查詢字串參數清單，且在 URL 中找到多個查詢字串參數時，所有值都會以分隔字元 *d* 分隔的清單傳回，分隔字元可以是單一字元或字元字串，如 " : " (空格-冒號-空格)。若省略 *d*，則各值之間不會使用分隔字元。若一個查詢字串參數的優先順序高於另一個，在同時找到兩者時，則應使用 *if* 陳述式，如下所示。

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

自&#x200B;*`getQueryParam`* 2.0 版起，此外掛程式即接受可選的第三個引數 *u*，此引數可讓您指定要從中擷取查詢字串參數的 URL。根據預設 (也就是將此第三個引數省略或保留為空白時)，此外掛程式會使用頁面 URL。例如，若您要從反向連結擷取查詢字串，您可以使用下列程式碼:

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

當必要的查詢字串參數出現在網址列中，而不是在目前頁框的 URL 時，即應在第三個引數中使用旗標 "f" 來搭配頁框:

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

使用頁框與 *f* 參數時，建議您使用 getValOnce 外掛程式，以防止在每次進行頁面檢視時都傳送促銷活動追蹤程式碼。*`getValOnce`*&#x200B;外掛程式，以防止在每次進行頁面檢視時都傳送促銷活動追蹤程式碼。

>[!NOTE]
>
>下列指示要求您變更網站上的資料收集代碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

**外掛程式程式碼**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 None
```


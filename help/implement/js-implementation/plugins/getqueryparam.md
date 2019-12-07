---
description: 若在現行頁面 URL 中找到指定的查詢字串參數值，則加以傳回。由於重要資料 (例如促銷活動追蹤程式碼、內部搜尋關鍵字等)都可在頁面上的查詢字串中使用，因此   getQueryParam 有助於將資料擷取至 Analytics 變數中。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getQueryParam
topic: Developer and implementation
uuid: ba202756-c728-4ebc-8fd9-5bc29a9f673b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getQueryParam

若在現行頁面 URL 中找到指定的查詢字串參數值，則加以傳回。由於重要資料 (例如促銷活動追蹤程式碼、內部搜尋關鍵字等)都可在頁面上的查詢字串中使用，因此   getQueryParam 有助於將資料擷取至 Analytics 變數中。

>[!IMPORTANT]
>
>此外掛程式僅限 H-Code 使用。[JavaScript 適用的 AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) 透過 [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md) 以原生方式提供此功能。

在 JavaScript 適用的 [!DNL AppMeasurement] 程式碼中安裝此外掛程式後，您即可選取要使用在查詢字串中找到的資料填入的 [!DNL Analytics] 變數，並指定所要擷取的查詢字串值，來設定外掛程式。外掛程式會偵測指定的查詢字串，若偵測到，即會以其值填入選擇的變數中。若沒有找到該值的查詢字串參數，則會返回空字串。若有查詢字串參數存在，但沒有值 (例如 `?param1&param2=value` 中的 param1)，則會傳回 *`true`* 這個字。

> [!NOTE]您必須在 JavaScript 適用的 [!DNL AppMeasurement] 程式碼中安裝此外掛程式的基礎程式碼，下列範例才能運作。

如果您想要使用 *`s.campaign`* 擷取可用的促銷活動追蹤程式碼，做為 *`cid`* 查詢參數的值，請在 JavaScript 適用的 [!DNL AppMeasurement] 程式碼的 *`doPlugins()`* 函數中輸入下列內容:

`s.campaign=s.getQueryParam('cid')`

在此範例中，若使用者進入您的網站時的登陸頁面 URL 為 [!DNL https://www.yoursite.com/index.html?cid=123456]，則 *`s.campaign`* 會收到 *123456* 的值。這可以用 [!DNL DigitalPulse] 偵錯器來檢視，其中應會將 *v0=123456* 顯示為影像要求的一部分。

> [!NOTE]參數 *`cid`* 與其他項目僅供範例說明之用。您可以將其替換為您的網站上任何現有的查詢字串參數。

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

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

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


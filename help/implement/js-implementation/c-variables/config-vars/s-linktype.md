---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 21f278017472ae39c6066ca7694a5cdbbfde41f3

---


# s.linkType

包含自動決定的連結類型 (若有的話)。可設為下列其中一項: 

    * 「d」（下載）
    * 「e」（退出）
    * 「o」（自訂／其他）

這是影像請求中的 `pe` 參數。If set with  [`linkURL`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkURL.html) or [`linkName`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html), a server call is sent as a download, custom, or exit link.

*注意：無法[`pageName`](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)為檔案下載、退出連結或自訂連結設定變數，因為每種連結類型都不是頁面檢視，也沒有關聯的頁面名稱。*


**範例**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

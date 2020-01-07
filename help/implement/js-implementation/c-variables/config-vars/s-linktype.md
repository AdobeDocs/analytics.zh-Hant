---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 21f278017472ae39c6066ca7694a5cdbbfde41f3

---


# s.linkType

包含自動決定的連結類型 (若有的話)。可設為下列其中一項: 

    *「d」(下載)
    *「e」(退出)
    *「o」(自訂/其他)

這是影像請求中的 `pe` 參數。若以 [`linkURL`](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkURL.html) 或 [`linkName`](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html) 設定，系統會將伺服器呼叫當作下載、自訂或退出連結進行傳送。

*注意: 變數[`pageName`](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)無法針對檔案下載、退出連結或自訂連結而設定，因為這些連結類型都不是頁面檢視，且不具有相關聯的頁面名稱。*


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

---
description: Analytics 提供數個變數，可用於收集 Analytics 資料。例如，pageName 變數中的值即為所要報告之網頁的名稱。本節列出 AppMeasurment 支援的變數。
keywords: Analytics實作；appmeasurement變數
seo-description: Analytics 提供數個變數，可用於收集 Analytics 資料。例如，pageName 變數中的值即為所要報告之網頁的名稱。本節列出 AppMeasurment 支援的變數。
seo-title: 變數概觀
solution: Analytics
subtopic: 變數
title: 變數概觀
topic: 開發人員和實施
uuid: 067d0135-572a-4a44-af9 e-445d3 c4 e9271
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 變數概觀

Analytics 提供數個變數，可用於收集 Analytics 資料。例如，pageName 變數中的值即為所要報告之網頁的名稱。本節列出 AppMeasurment 支援的變數。

如需每個變數如何顯示在 Analytics 報表中的列表，請參閱[變數 - 在報告中如何使用](https://marketing.adobe.com/resources/help/en_US/reference/?f=variable_definitions)。

<!-- 

<p>The following is for a client issue reported by Gundy on 1/22/16 in an email "Documentation and JavaScript Update Request". This may be a KB issue. Awaiting word from Russ. - Blake </p>

 -->

## 如何設定變數 {#section_E52CF9E8FDF74164A1511E0D9D31884D}

AppMeasurement requires that all configuration variables be set before the initial call to the track function, *`t()`*. If configuration variables are set after the call to *`t()`*, unexpected results may occur.

Configuration variables are set inside the *`doPlugins`* function, which is called during the execution of the track function. The specific configuration variable causing this issue is *`trackInlineStats`*, which enables ClickMap data collection. 此會使 ClickMap 模組處於未判斷狀態，並導致第一個追蹤呼叫附加「未定義」字串至 Adobe Analytics 信標，並影響貨幣代碼。

若要解決此問題，請移除所有 doPlugins 函數上的設定變數。

```
/************************** CONFIG SECTION **************************/ 
/* Ensure these variables are correct before deploying */ 
var s_account="[INSERT-REPORT-SUITE-ID-HERE]" 
var s=s_gi(s_account) 
s.trackingServer="[INSERT-TRACKING-SERVER-HERE]" 
s.visitorNamespace="[INSERT-VISITOR-NAMESPACE-HERE]" 
s.charSet="ISO-8859-1" 
s.currencyCode="USD" 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" 
s.linkInternalFilters="javascript:,three,two,one,dev16,.,nike" 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.debugTracking=true 
 
s.usePlugins=true; 
function s_doPlugins(s) { 
    //add your custom plugin code here 
} 
s.doPlugins=s_doPlugins; 
 
/* 
============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.5.3 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at https://www.omniture.com 
*/ 
function AppMeasurement(){var a=this;a.version="1.5.3";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.zb;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.ob=function(a){try{console.log(a)}catch(b){}};a.za=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a|| 
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.gb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&& 
```


---
description: Analytics 提供數個變數，可用於收集 Analytics 資料。例如，pageName 變數中的值即為所要報告之網頁的名稱。本節列出 AppMeasurment 支援的變數。
keywords: Analytics Implementation;appmeasurement variables
subtopic: Variables
title: 變數概觀
topic: Developer and implementation
uuid: 067d0135-572a-4a44-af9e-445d3c4e9271
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 變數概觀

Analytics 提供數個變數，可用於收集 Analytics 資料。例如，pageName 變數中的值即為所要報告之網頁的名稱。本節列出 AppMeasurement 支援的變數。

如需頁面變數的相關詳細資訊，請前往[這裡](/help/implement/js-implementation/page-variables/page-variables.md)。
如需設定變數的相關詳細資訊，請前往[這裡](/help/implement/js-implementation/c-variables/configuration-variables.md)。

## 如何設定變數

AppMeasurement 要求所有設定變數都須於初始呼叫追蹤函數 *`t()`* 前完成設定。如果設定變數是在呼叫 *`t()`* 後設定，可能會發生未預期的結果。

設定變數是在 *`doPlugins`* 函數內設定，這會在執行追蹤函數期間呼叫。導致此問題的特定設定變數為 *`trackInlineStats`*，這會啟用 ClickMap 資料收集。此會使 ClickMap 模組處於未判斷狀態，並導致第一個追蹤呼叫附加「未定義」字串至 Adobe Analytics 信標，並影響貨幣代碼。

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


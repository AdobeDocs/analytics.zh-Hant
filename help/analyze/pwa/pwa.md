---
title: Analytics 專用 PWA
description: Adobe Analytics 專用漸進式網頁應用程式
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics 專用 PWA

本指南說明如何搭配使用 Adobe Analytics 與漸進式網頁應用程式 (PWA)。

## 簡介

PWA 可為網站提供原生應用程式體驗及離線功能。PWA 通常會包含服務程式、快取佈建和資訊清單檔案，這些都有助於實現更短的載入時間、更輕鬆的導覽操作，以及快速回應。

Adobe Analytics 與 PWA 搭配運作的順暢程度，與傳統網站如出一轍。雖然要讓 PWA 本身和內部以漸進方式運作，必須額外符合幾項要求，但 PWA 不會造成任何阻礙或限制，而導致 Analytics 收集或回報資料的方式與傳統網站有所不同。事實上，由於 Analytics 已具備離線追蹤功能，PWA 可協助您運用這項內建功能，且過程比傳統網站更為輕鬆。

## 取得 PWA Analytics 資料

您不需要變更任何設定，即可透過 Analytics 收集和分析 PWA 資料。Analytics 會自動提供與傳統網站相同的所有功能和特色。

## 新增離線追蹤功能以提高 PWA 效益

您可以搭配使用 Analytics [離線追蹤功能](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html)，提高 PWA 的使用效益。此功能預設為關閉，但只要將下列屬性新增至 AppMeasurement.js 檔案即可開啟：`s.trackOffline=true;`。

例如，下列 AppMeasurement.js 檔案中，將該屬性新增至 `CONFIG SECTION` 的結尾處：

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
***
    
```


如需編輯 AppMeasurement.js 檔案的詳細資訊，請參閱[在 AppMeasurement.js 檔案中插入程式碼](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

如需 AppMeasurement.js 檔案的設定範例，請參閱[設定 AppMeasurement.js 檔案](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)。

如需 AppMeasurement.js 檔案特性的詳細資訊，請參閱 [Javascript 實作概述](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。

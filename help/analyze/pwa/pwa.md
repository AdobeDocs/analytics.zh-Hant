---
title: Analytics適用的PWA
description: Adobe Analytics的漸進式網頁應用程式
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics適用的PWA

本指南說明如何搭配使用Adobe Analytics與漸進式網頁應用程式(PWA)。

## 簡介

PWA可為網站提供原生應用程式體驗以及離線功能。 通常，PWA包括服務工作者、快取設定和資訊清單檔案，這些功能都有助於加快載入時間、更輕鬆的導覽和回應式行為。

Adobe Analytics與PWA搭配運作的順暢程度與傳統網站的順暢度相同。 雖然PWA需要多一些要求，才能逐漸地在內部和內部運作，但Analytics收集或報告資料的方式並不會造成任何障礙或限制，與傳統網站不同。 事實上，由於Analytics已包含離線追蹤功能，PWA可協助您比傳統網站更輕鬆地運用此內建功能。

## 取得您的PWA Analytics資料

若要使用Analytics收集和分析PWA資料，您不需要進行任何設定變更。 Analytics會自動提供與傳統網站相同的所有功能和功能。

## 新增離線追蹤以提高PWA效能

您可以搭配使用Analytics離線追蹤功能來提 [高PWA](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) 的效能。 依預設，此功能已關閉，但您可以將下列屬性新增至AppMeasurement.js檔案以開啟： `s.trackOffline=true;`。

例如，在下列AppMeasurement.js檔案中，屬性會新增至結尾 `CONFIG SECTION`:

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


如需編輯AppMeasurement.js檔案的詳細資訊，請參 [閱將程式碼插入AppMeasurement.js檔案](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

如需AppMeasurement.js檔案中設定的範例，請參 [閱設定AppMeasurement.js檔案](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)。

如需AppMeasurement.js檔案特性的詳細資訊，請參閱 [Javascript實作概觀](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。

---
title: 適用於Analytics的PAs
seo-title: 適用於Analytics的PAs
description: Adobe Analytics的漸進式網頁應用程式
seo-description: 搭配Analytics使用PACE
translation-type: tm+mt
source-git-commit: f64e5d9977bebd0e9db4af0f7118e9e64978c1c7

---


# 適用於Analytics的PAs

本指南說明如何搭配使用Adobe Analytics與漸進式Web Apps(PHOST)。

## 簡介

PIAs可為網站提供原生應用程式體驗以及離線功能。通常PHOST包括服務工作者、快取規定和資訊清單檔案，這些都能協助加快載入時間、更輕鬆的導覽以及回應式行為。

Adobe Analytics與傳統網站一樣順暢地運作。雖然Pare有一些更多的要求以漸進式方式運作，但並不會對Analytics收集或報告與傳統網站不同的資料造成任何阻礙或限制。事實上，由於Analytics已包含離線追蹤功能，PASE可協助您比傳統網站更輕鬆地運用這項建置功能。

## 取得您的PWA分析資料

若要透過Analytics收集及分析PVA資料，您不需要進行任何變更。Analytics會自動提供與傳統網站相同的功能和功能。

## 新增離線追蹤以提高PWA效能

您可以使用Analytics [離線追蹤功能](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) 來提高PVA的效能。依預設，此功能會關閉，但您可以將下列屬性新增至AppMeasurement. js檔案，以便開啓： `s.trackOffline=true;`。

例如，在下列AppMeasurement. js檔案中，屬性會新增 `CONFIG SECTION`至：

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


如需編輯AppMeasurement. js檔案的詳細資訊，請參閱 [「插入程式碼至AppMeasurement. js檔案](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)」。

如需AppMeasurement. js檔案中設定的範例，請參閱 [設定AppMeasurement. js檔案](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)。

如需AppMeasurement. js檔案特性的詳細資訊，請參閱 [Javascript實施概述](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。

---
title: Analytics 專用 PWA
description: Adobe Analytics 專用漸進式網頁應用程式
role: Business Practitioner, Administrator
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
translation-type: tm+mt
source-git-commit: 3f3a9b7f81ce671a94b7fe71c3ef7e4ae206b875
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 78%

---

# Adobe Analytics 專用 PWA

本頁面說明如何搭配漸進式網頁應用程式 (PWA) 使用 Adobe Analytics。

## 簡介

PWA 可為網站提供原生應用程式體驗及離線功能。PWA 通常會包含服務程式、快取佈建和資訊清單檔案，這些都有助於實現更短的載入時間、更輕鬆的導覽操作，以及快速回應。

Adobe Analytics與PWA的合作與傳統網站一樣順暢。 雖然要讓 PWA 本身和內部以漸進方式運作，必須額外符合幾項要求，但 PWA 不會造成任何阻礙或限制，而導致 Analytics 收集或回報資料的方式與傳統網站有所不同。事實上，由於 Analytics 已具備離線追蹤功能，PWA 可協助您運用這項內建功能，且過程比傳統網站更為輕鬆。

## 取得 PWA Analytics 資料

您無須變更任何設定，即可透過 [!UICONTROL Analytics] 收集和分析 PWA 資料。[!UICONTROL Analytics ]會自動提供與傳統網站相同的所有功能和特色。

## 新增離線追蹤功能以提高 PWA 效益

PWA 可與 Adobe Analytics [離線追蹤功能](/help/implement/vars/config-vars/trackoffline.md)搭配使用，提高使用效益。此功能預設為關閉，但只要將下列屬性新增至 AppMeasurement.js 檔案即可開啟：`s.trackOffline=true;`。

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

如需編輯AppMeasurement.js檔案的詳細資訊，請參閱「插入核心AppMeasurement代碼](/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md)」。[

如需設定AppMeasurement.js檔案的詳細資訊，請參閱[設定變數概述](/help/implement/vars/config-vars/configuration-variables.md)以及相同子章節中個別變數專屬頁面。

如需AppMeasurement.js檔案特性的詳細資訊，請參閱[JavaScript實作概觀](/help/implement/js/overview.md)。

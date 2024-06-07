---
title: Analytics 專用 PWA
description: Adobe Analytics 專用漸進式網頁應用程式
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: ht
source-wordcount: '277'
ht-degree: 100%

---

# Adobe Analytics 專用 PWA

本頁面說明如何搭配漸進式網頁應用程式 (PWA) 使用 Adobe Analytics。

## 簡介

PWA 可為網站提供原生應用程式體驗及離線功能。PWA 通常會包含服務程式、快取佈建和資訊清單檔案，這些都有助於實現更短的載入時間、更輕鬆的導覽操作，以及快速回應。

Adobe Analytics 與 PWA 搭配運作的順暢程度，與傳統網站如出一轍。雖然要讓 PWA 本身和內部以漸進方式運作，必須額外符合幾項要求，但 PWA 不會造成任何阻礙或限制，而導致 Analytics 收集或回報資料的方式與傳統網站有所不同。事實上，由於 Analytics 已具備離線追蹤功能，PWA 可協助您運用這項內建功能，且過程比傳統網站更為輕鬆。

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

若要了解更多關於設定 AppMeasurement.js 檔案，請參閱 [設定變數概覽](/help/implement/vars/config-vars/configuration-variables.md) 以及相同子章節內的個別變數特定頁面。

若要了解更多關於編輯 AppMeasurement.js 檔案特性，請參閱 [Javascript 實施概覽](/help/implement/js/overview.md)。

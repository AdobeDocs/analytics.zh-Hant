---
description: 如何在 Adobe Analytics 實施作業程式碼中合併 AppMeasurement 程式庫和 Activity Map 模組的範例
title: 檢視 Activity Map 實施作業程式碼的範例
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: d7ca35df-8fbe-4e87-b1e9-e1a77d5f420f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '53'
ht-degree: 100%

---

# 實施作業代碼範例{#sample-implementation-code}

## AppMeasurement.js 範例檔案

以下是如何在 [!DNL AppMeasurement.js] 檔案中結合 AppMeasurement 程式庫和 Activity Map 模組的範例。

```
// Initialize AppMeasurement 
 var s_account="INSERT-RSID-HERE" 
 var s=s_gi(s_account)
  
/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/ 
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE") 
  
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
/* uncomment below to use doPlugins */ 
/* s.usePlugins=true 
function s_doPlugins(s) { 
// use implementation plug-ins that are defined below 
// in this section. For example, if you copied the append 
// list plug-in code below, you could call: 
// s.events=s.apl(s.events,"event1",",",1); 
} 
s.doPlugins=s_doPlugins */ 
  
/* WARNING: Changing any of the below variables will cause drastic 
changes to how your visitor data is collected. Changes should only be 
made when instructed to do so by your account manager.*/ 
s.trackingServer="INSERT-TRACKING-SERVER-HERE" 
s.trackingServerSecure="INSERT-SECURE-TRACKING-SERVER-HERE" 
  
/************************** PLUGINS SECTION *************************/ 
// copy and paste implementation plug-ins here - See "Implementation Plug-ins" @ 
// https://docs.adobe.com/content/help/en/analytics/implementation/vars/plugins/impl-plugins.html 
// Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** START Activity Map MODULE *****************************/ 
 //The following module enables ActivityMap tracking in Adobe Analytics. ActivityMap 
  allows you to view data overlays on your links and content to understand how 
  users engage with your web site. If you do not intend to use ActivityMap, you 
  can remove the following block of code from your AppMeasurement.js file.
  Additional documentation on how to configure Activity Map is available at: 
  https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-admins/activitymap-enable.html 
 */ 
 function AppMeasurement_Module_Activity Map(g){func 
 ...
 /* END Activity Map MODULE */ 
/* 
 ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.6 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at https://www.adobe.com/marketing-cloud.html 
*/ 
function AppMeasurement(){var a=this;a.version= 
...
```

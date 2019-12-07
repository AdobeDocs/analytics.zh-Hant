---
description: 本節包含核心 JavaScript 檔案與網站頁面的範例程式碼。
keywords: Analytics Implementation;appmeasurement.js code;example page code
subtopic: JavaScript AppMeasurement
title: 範例頁面程式碼和全域設定
topic: Developer and implementation
uuid: e8880d77-172b-42e5-8187-ce371aa9eff9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 範例頁面程式碼和全域設定

本節包含核心 JavaScript 檔案與網站頁面的範例程式碼。

>[!IMPORTANT]
>
>此範例使用訪客 ID 服務，這已部署為 [JavaScript 實施](/help/implement/js-implementation/javascript-implementation-overview.md)的一部分。將訪客 API JavaScript 檔案加入所有網站頁面前就先在 AppMeasurement 中啟用訪客 ID 服務，會造成重複訪客計數。為了避免重複訪客計數，請務必了解並遵循[訪客 ID 服務](/help/implement/js-implementation/c-unique-visitors/visid-service.md)。

## AppMeasurement.js 範例程式碼 {#section_4351543F2D6049218E18B48769D471E2}

>[!IMPORTANT]
>
>設定變數應在 *`doPlugins`* 函數之上設定。

若是新的實施，您可將下列全域組態程式碼貼到 AppMeasurement.js 檔案的開頭，以開始使用:

```js
//initialize AppMeasurement 
var s_account="INSERT-RSID-HERE" 
var s=s_gi(s_account) 
 
/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/ 
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE") 
 
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
changes to how your visitor data is collected.  Changes should only be 
made when instructed to do so by your account manager.*/ 
s.trackingServer="INSERT-TRACKING-SERVER-HERE" 
s.trackingServerSecure="INSERT-SECURE-TRACKING-SERVER-HERE" 
 
/************************** PLUGINS SECTION *************************/ 
 
// copy and paste implementation plug-ins here - See "Implementation Plug-ins" @ 
// https://marketing.adobe.com/resources/help/en_US/sc/implement/#Implementation_Plugins 
// Plug-ins can then be used in the s_doPlugins(s) function above  
 
/****************************** MODULES *****************************/ 
 
// copy and paste implementation modules (Media, Integrate) here 
// AppMeasurement_Module_Media.js - Media Module, included in AppMeasurement zip 
// AppMeasurement_Module_Integrate.js - Integrate Module, included in AppMeasurement zip 
 
/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  
```

## 頁面程式碼範例 {#section_042412C29CC249E298F19B2BC2F43CE7}

若是新的實施，您可將下列頁面程式碼貼到您要追蹤之頁面上的開頭 <body> 標籤的後面:

```js
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
var s_code=s.t();if(s_code)document.write(s_code)//--></script>
```

也務必在每一頁上加入對 `AppMeasurement.js` 和 `VisitorAPI.js` 的參考。如需指示，請參閱 [JavaScript 實施](/help/implement/js-implementation/javascript-implementation-overview.md)。

---
description: Apl (或 AppendList) 外掛程式可讓您為任何分隔清單附加值，透過區分大小寫或不區分大小寫檢查的選項確認該數值不在清單中。Apl 外掛程式被多個標準外掛程式所參照，但也能直接應用於多種情況。
keywords: Analytics Implementation
subtopic: Plug-ins
title: appendList
topic: Developer and implementation
uuid: e923c86c-eaa6-4e17-a3a4-0e08af886674
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# appendList

Apl (或 AppendList) 外掛程式可讓您為任何分隔清單附加值，透過區分大小寫或不區分大小寫檢查的選項確認該數值不在清單中。Apl 外掛程式被多個標準外掛程式所參照，但也能直接應用於多種情況。

此外掛程式適用於:

* 新增一個事件至當前事件變數
* 無需複製清單內數值新增一個數值至清單變數
* 基於一些頁面邏輯新增產品至當前產品變數
* 新增數值至參數&#x200B;*`linkTrackVars`* 和 *`linkTrackEvents`*

**使用案例 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>藍本 </p> </td> 
   <td colname="col2"> <p>Add <span class="term"> event1 </span> to the current events variable while ensuring the event isn't duplicated. </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>程式碼 </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>結果 </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**使用案例 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>藍本 </p> </td> 
   <td colname="col2"> <p>新增數值  <span class="term">history</span> 至清單變數 <span class="varname">prop1</span>，並將 <span class="term">history</span> 和 <span class="term">History</span> 視為同一個值。 </p> <p>s.prop1="Science,History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>程式碼 </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>結果 </p> </td> 
   <td colname="col2"> <p>s.prop1="Science,History" </p> <p> 不會新增 <span class="term">history</span>，因為 <span class="term">History</span> 已在清單中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE]下列指示會要求您變更網站上的資料收集程式碼。此動作可能會影響到您網站上的資料收集，因此應由懂得使用及實施 [!DNL Analytics] 的開發人員執行。

## 實施 {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

請遵循下列步驟，實施 APL 外掛程式。

1. 向客戶服務或您目前指派的 Adobe 顧問索取外掛程式的程式碼。
1. 視需要在 *`s_doPlugins`* 函數內將呼叫新增至 API 函數

以下是程式碼在您的網站上可能呈現的樣貌:

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**受支援的瀏覽器**

此外挂程式要求瀏覽器支援 JavaScript 版本 1.0。

**外掛程式資訊**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 外掛程式資訊 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>參數 </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L= 來源清單，可以是空清單 </p> <p> v= 要附加的數值 </p> <p> d = 清單分隔字元 </p> <p> u (可選，預設為 0) 特定值檢查。0=無特定值檢查，始終附加數值。1=不區分大小寫的檢查，僅當數值不在清單中時附加。2=區分大小寫的檢查，僅當數值不在清單中時附加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>返回值 </p> </td> 
   <td colname="col2"> <p>原始清單，如果新增數值則帶有被附加的數值 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用範例 </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

來源清單 L 可以為空，例如&#x200B;*`L=""`*。返回值可以是空的清單或者是具有一個數值的清單。

**外掛程式程式碼**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 s.split
```


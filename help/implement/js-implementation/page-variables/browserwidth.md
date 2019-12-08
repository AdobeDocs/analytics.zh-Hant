---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# browserWidth

 變數會顯示瀏覽器視窗的寬度。


<!-- 

browserwidth.xml

 -->

此變數會在頁面程式碼執行後、*`doPlugins`* 執行前填入。

> [!NOTE]此變數僅供讀取，絕不可設定。

您可以讀取這些值，並將其複製到 prop/eVar 中，但絕不可加以變更。此變數是隨 JavaScript 檔案的 H.11 版導入的。

**參數**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>查詢參數</b> </p> </td> 
   <td> <p> <b>值</b> </p> </td> 
   <td> <p> <b>範例</b> </p> </td> 
   <td> <p> <b>受影響的報表</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>正整數 </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>流量 &gt; 技術 &gt; 瀏覽器寬度 </p> </td> 
  </tr> 
 </tbody> 
</table>

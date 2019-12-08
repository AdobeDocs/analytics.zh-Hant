---
description: 顯示訪客在到達您網站前的網域或 URL、訪客找到您的網站時所使用的方法，以及由這些反向連結位置產生的瀏覽次數。
title: 反向連結
topic: Reports
uuid: e63b47b4-49f3-43af-8409-3272bec0484e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 反向連結

顯示訪客在到達您網站前的網域或 URL、訪客找到您的網站時所使用的方法，以及由這些反向連結位置產生的瀏覽次數。

例如，如果訪客從網站 A 點按連結找到您的網站，如果網站 A 沒有定義為您的網域的一部分，它就是反向連結。在實施中，您的實施顧問會幫助您定義屬於您網站一部分的網域和 URL。(此變更在實作期間後即可完成。) 

任何非這些已定義網域和 URL 之一部分的網域或 URL，就會被視為反向連結。例如，將網頁 A 和網頁 B 新增至內部 URL 篩選器，但網頁 C 沒有加入。在這種情形下，網頁 C 就會被視為反向連結。

## 分配、過期和特殊值 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marketing Reports &amp; Analytics (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad hoc analytics </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 量度分配 </td> 
   <td colname="col2"> 最近 </td> 
   <td colname="col3"> 最近 </td> 
   <td colname="col4"> 最近 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值過期時間 </td> 
   <td colname="col2"> 瀏覽 </td> 
   <td colname="col3"> 瀏覽 </td> 
   <td colname="col4"> 瀏覽 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值限制 </td> 
   <td colname="col2"> 無限制 (未來版本可能有所變動) </td> 
   <td colname="col3"> 無限制 (未來版本可能有所變動) </td> 
   <td colname="col4"> 無 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特殊值 </td> 
   <td colname="col2"> <p>「無」: 瀏覽期間沒有反向連結的全網站總計。 </p> </td> 
   <td colname="col3"> <p>「無」: 瀏覽期間沒有反向連結的全網站總計。 </p> </td> 
   <td colname="col4"> <p> 空白 - 等於「無」，瀏覽期間沒有反向連結的全網站總計。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 附註 {#section_B83A3571D64E4E7792712FAF740D7955}

* 反向連結、反向連結類型和反向連結網域設定於瀏覽的第一次點擊，或是在反向連結為外部的瀏覽期間 (例如，假設訪客離開您的網站、使用搜尋引擎，然後在第一次瀏覽過期前返回您的網站)。這些值會同時設定，且持續存在於瀏覽期間。
* 會篩選內部 URL。只有不符合內部 URL 篩選器的反向連結才會列在此報告中。
* 對應的量度在 Ad Hoc Analysis 中稱為「反向連結例項」。
* 分類/建立書籤值不列在「反向連結」報告中。這表示全網站瀏覽值不符合此報告的瀏覽值。

## 報告歷史記錄 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 變更 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2014 年 1 月 16 日 </td> 
   <td colname="col2"> Data Warehouse 已更新為符合 Marketing Reports &amp; Analytics 使用的邏輯。在此日期前，搜尋關鍵字不會持續存在於瀏覽期間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6/19/2012 </td> 
   <td colname="col2"> <p> 在 2012 年 7 月前，「無」包含所有行動流量、分類/建立書籤和無 JavaScript 的瀏覽。在 2012 年 7 月後，「無」僅包含瀏覽第一頁上無 JavaScript 的點擊。 </p> </td> 
  </tr> 
 </tbody> 
</table>


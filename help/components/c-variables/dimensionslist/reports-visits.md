---
description: 顯示指定時段內整個網站的造訪次數。
title: 瀏覽
topic: Reports
uuid: ff65bddf-fb65-4cf0-8aae-4ab59c2bb0a7
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 瀏覽

顯示指定時段內整個網站的造訪次數。

**報告屬性**

* 瀏覽的定義是一系列間隔時間不超過 30 分鐘的連續頁面檢視，或連續 12 小時的活動。
* 一次瀏覽到期後，會在後續提出任何影像要求時起始新瀏覽。
* 一個訪客通常至少會有一個 (但可能超過一個) 瀏覽。
* 當新訪客提出第一個影像要求時，或現有使用者的瀏覽到期後，瀏覽即會開始。我們可將其視為登入頁面。
* 瀏覽到期前的最後一個影像要求出現時，瀏覽即結束。我們可將其視為退出頁面。

   請參閱[登入與退出報告](/help/components/c-variables/dimensionslist/reports-entries-exits.md)。
* 以小時為單位的劃分會以報表套裝的時區為準。
* 此報告不含明細項目。您只能在趨勢格式中加以檢視。
* 詳細程度可採用小時、日、週、月、季與年。這些詳細程度設定是否可用，須取決於報告日期範圍。

請參閱[瀏覽量度](/help/components/c-variables/c-metrics/metrics-visit.md)，以進一步瞭解 Experience Cloud 對此量度的處理方式。

**產品特定報告資訊**

<table id="table_3138CA443CAC4F55838216E8B8786EE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 產品 </th> 
   <th colname="col2" class="entry"> 導覽 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 網站量度</span> &gt; <span class="uicontrol">造訪</span> </p> <p>您可以對選定頁面執行<span class="wintitle">「造訪報表」</span>。跨午夜的造訪會同時計入造訪開始的那一天與結束的那一天。但指定日期範圍的總計會進行去重複化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad Hoc Analysis </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 報告</span> &gt; <span class="uicontrol">網站量度</span> &gt; <span class="uicontrol">瀏覽</span> </p> 
    <ul id="ul_73FEE02C129041D6A63F2DB07676960F"> 
     <li id="li_CC3BB22DE97941EB8032BE4421FFC173"> 您可依幾乎所有的其他報告與變數來劃分此報告中的每個項目，讓您以任何詳細程度檢視劃分內容。 </li> 
     <li id="li_D53D480D73264D47945C9E1202B7BD4F">跨午夜的造訪會同時計入造訪開始的那一天與結束的那一天。但指定日期範圍的總計會進行去重複化。 </li> 
     <li id="li_B8BCC584F95B407DB87F5EA57CC88F62">您可以在此報告中使用所有的轉換與流量量度，並可對各種轉換量度使用不同的配置。 </li> 
     <li id="li_0F342D3DCFF44ABAB79BD0F9E7F43E1E">此報告可使用多個高度進階區段。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


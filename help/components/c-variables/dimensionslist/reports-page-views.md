---
description: 此為趨勢報告，顯示選取時段 (小時、日、週、月份、季度或年) 內網站頁面的檢視次數。您可利用此報告來追蹤網站中每個頁面的檢視次數，以及整個網站的頁面檢視次數總和。
title: 頁面檢視
topic: Reports
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
translation-type: tm+mt
source-git-commit: 707b61d853a8ec68b3f77a35a1aa5f0c7dd8a1fd

---


# 頁面檢視

此為趨勢報告，顯示選取時段 (小時、日、週、月份、季度或年) 內網站頁面的檢視次數。您可利用此報告來追蹤網站中每個頁面的檢視次數，以及整個網站的頁面檢視次數總和。

[頁面檢視](/help/components/c-variables/c-metrics/metrics-page-view.md)是對整頁文件的要求，而不是對頁面的某個元素，例如影像或影片的要求。例如，若單一訪客在一次瀏覽期間檢視 15 個頁面，則計為 15 次頁面檢視。若訪客在一次瀏覽期間檢視相同頁面 3 次，則計為 3 次頁面檢視。

## 報表屬性

* This report references the number of times the [`t()`](/help/implement/vars/functions/t-method.md) method is called on your site.
* 使用此方法的連結追 [`tl()`](/help/implement/vars/functions/tl-method.md) 蹤呼叫不會計入此報表。
* 由於只要使用者重新整理頁面或點按上一頁按鈕就會傳送影像要求，因此這個報告也會包含這些動作。
* 以小時為單位的劃分會以報表套裝的時區為準。
* 此報告不含明細項目。因此，此報告只能以趨勢格式檢視。
* 詳細程度可採用小時、日、週、月、季與年。這些詳細程度是否可用須取決於報告日期範圍。

## 產品特定資訊

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 網站內容</span> &gt; <span class="uicontrol">頁面檢視</span> </p> <p>此報告可使用區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ad hoc analysis </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> 依所有其他報告與變數來劃分此報告中的每個項目，讓您以任何詳細程度檢視劃分內容。 </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">您可以在此報告中使用所有的轉換與流量量度，並可對所有轉換量度使用不同的配置。 </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">此報告可使用多個高度進階區段。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


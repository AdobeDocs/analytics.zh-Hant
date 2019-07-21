---
description: Analytics 中使用的自訂變數清單。
keywords: Analytics 實施
seo-description: Analytics 中使用的自訂變數清單。
seo-title: 自訂變數
solution: Analytics
title: 自訂變數
topic: 開發人員和實施
uuid: 54adf622-7f05-49c0-b7 e6-702bb2 f17 b1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 自訂變數

Analytics 中使用的自訂變數清單。

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> 變數 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 流量變數 </td> 
   <td> 檢查 prop1 - 75 的值。以下是要檢查之項目的檢查清單。 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">大小寫的使用是否正確？"ValueA" 與 "valueA" 是不同的記錄。您可以全部使用小寫，因為少部分的瀏覽器會將所有變數轉換為小寫。 </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">值的長度是否小於 100 個字元？若非如此，值的某些部分可能會截斷。 </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> 在單一屬性變數中，是否所有的值都相關聯，還是有部分值可能不適用？ </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> 轉換變數 </td> 
   <td> <span class="wintitle">Econversion</span> 變數包含 eVar 1 - 75。以下是所要檢查的問題清單。 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">大小寫的使用是否正確？"ValueA" 與 "valueA" 是不同的記錄。您可以全部使用小寫，因為少部分的瀏覽器會將所有變數轉換為小寫。 </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">值的長度是否小於 255 個字元？若非如此，值的某些部分可能會截斷。 </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">在單一 eVar 中，是否所有的值都相關聯，還是有部分值可能不適用？ </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> 自訂事件 </td> 
   <td> 事件中包含標準值 (<span class="wintitle">prodView</span>、<span class="wintitle">scOpen</span>、<span class="wintitle">scAdd</span>、<span class="wintitle">scCheckout</span>、<span class="wintitle">purchase</span>) 以及從 event1 到 event100 的自訂事件。所有事件都會以事件變數傳送。相同頁面上的多個事件應以逗號分隔 (而非空白字元)。 
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">對於所有的標準轉換事件，產品也應以適用的產品填入。對於購買以外的所有事件，數量和價格都是選用元素。 </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108"><span class="wintitle">購買</span>事件只需在購買完成並確認後，在工作階段中設定一次。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


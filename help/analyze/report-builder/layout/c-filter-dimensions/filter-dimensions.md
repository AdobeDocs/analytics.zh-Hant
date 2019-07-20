---
description: 您可以篩選新增至「列標籤」格線的維度。篩選能減少請求傳回的資料數量，您可以從「樞紐配置」或「自訂配置」套用篩選。在「樞紐配置」中設定維度篩選時，您可以額外指定來自儲存格的項目數量。
seo-description: 您可以篩選新增至「列標籤」格線的維度。篩選能減少請求傳回的資料數量，您可以從「樞紐配置」或「自訂配置」套用篩選。在「樞紐配置」中設定維度篩選時，您可以額外指定來自儲存格的項目數量。
seo-title: 篩選維度概述
solution: Analytics
title: 篩選維度概述
topic: Report Builder
uuid: c54d5add-f278-476d-8f14-73f1 c2 e37671
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 篩選維度概述

您可以篩選新增至「列標籤」格線的維度。篩選能減少請求傳回的資料數量，您可以從「樞紐配置」或「自訂配置」套用篩選。在「樞紐配置」中設定維度篩選時，您可以額外指定來自儲存格的項目數量。

系統現在會根據您在 Report Builder 請求中所選的元素和度量，輸入選取的篩選條件表單。

## Define filter - values and special characters {#section_15840216A4044C40974945FAA435AD93}

Information about filters in the **[!UICONTROL Most Popular Filter]** &gt; **[!UICONTROL Define Filter]** panel.

![](assets/define_filter.png)

下列表格會提供篩選的範例和相關資訊:

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 篩選器 </th> 
   <th colname="col02" class="entry"> 說明 </th> 
   <th colname="col2" class="entry"> 範例篩選器 </th> 
   <th colname="col3" class="entry"> 比對結果 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>包含所有字詞 </p> </td> 
   <td colname="col02"> <p>包含每個以空格分隔的值，順序不拘。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>會比對<span class="term"> b cand</span><span class="term"> b a c</span>等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含任何字詞 </p> </td> 
   <td colname="col02"> <p>包含至少其中一個篩選器 (以空格分隔)。 </p> </td> 
   <td colname="col2"> <p>ABC </p> </td> 
   <td colname="col3"> <p>會比對<span class="term"> A</span>1、 <span class="term"> B2</span>、 <span class="term"> C但</span>不是 <span class="term"> D4</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含片語 </p> </td> 
   <td colname="col02"> <p>包含搜尋篩選器，也可能包含其他詞語。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>會比對<span class="term"> abc</span> 和 <span class="term"> abc def</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含任何字詞 </p> </td> 
   <td colname="col02"> <p>傳回不包含您輸入值的所有項目。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>會比對<span class="term"> d e f</span> 但不是 <span class="term"> c d f</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含此片語 </p> </td> 
   <td colname="col02"> <p>傳回不包含您片語的所有項目。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>排除<span class="term"> abc</span>， <span class="term"> abc def</span> ，與 <span class="term"> def相符</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>等於 </p> </td> 
   <td colname="col02"> <p>傳回完全相符的項目。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> 會傳回，而不是其他項目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不等於 </p> </td> 
   <td colname="col02"> <p>傳回與您輸入的值不完全相符的所有項目。 </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>不符合 <span class="term"> a</span>. </p> <p>Matches <span class="term"> a b c</span>. </p> <p>Matches <span class="term"> abc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開始於 </p> </td> 
   <td colname="col02"> <p>傳回以特定值作為開頭的結果。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>會比對<span class="term"> abcd</span> 但不 <span class="term"> 是abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>終止於 </p> </td> 
   <td colname="col02"> <p>傳回以特定值作為結尾的結果。 </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>會比對<span class="term"> wxyz</span> 但not <span class="term"> wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>進階 (特殊字元) </p> </td> 
   <td colname="col02"> <p>可讓您使用規則運算式字元: </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Home*Page$" | sports </p> </td> 
   <td colname="col3"> <p> 這會定義一個篩選器，開始於<span class="term"> 「首頁」</span>，然後尋找零個或多個字元，然後以 <span class="term"> 「頁面</span>」結尾。 </p> <p>Also, any page with <span class="term"> sports</span> in it. </p> <p>以下是一些比對的範例: </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">Home 和 (其他字元) Page </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">Home sports </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">sports Page </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">sports </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sports abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特殊字元 </th> 
   <th colname="col2" class="entry"> 用途 </th> 
   <th colname="col3" class="entry"> 附註 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> 等於 </td> 
   <td colname="col3"> <p>除非未與另一個引號成對，否則不會予以逸出。例如，<span class="term"> 17「顯示</span> 不是片語。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> 萬用字元 </td> 
   <td colname="col3"> <p>與規則運算式中使用的星號相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> 開始於 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> 終止於 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> 否 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> 或 </td> 
   <td colname="col3"> <p>只有在<span class="term"> 進階(特殊字元)</span> 篩選。 </p> </td> 
  </tr> 
 </tbody> 
</table>
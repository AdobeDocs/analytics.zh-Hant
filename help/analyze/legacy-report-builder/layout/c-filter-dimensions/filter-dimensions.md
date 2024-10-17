---
description: 您可以篩選新增至「列標籤」格線的維度。篩選能減少請求傳回的資料數量，您可以從「樞紐配置」或「自訂配置」套用篩選。在「樞紐配置」中設定維度篩選時，您可以額外指定來自儲存格的項目數量。
title: 篩選維度概觀
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 73%

---

# 篩選維度概觀

{{legacy-arb}}

您可以篩選新增至「列標籤」格線的維度。篩選能減少請求傳回的資料數量，您可以從「樞紐配置」或「自訂配置」套用篩選。在「樞紐配置」中設定維度篩選時，您可以額外指定來自儲存格的項目數量。

系統會根據Report Builder請求中所選的元素和量度，填入選取的篩選條件表單。

## 定義篩選 – 值與特殊字元 {#section_15840216A4044C40974945FAA435AD93}

在&#x200B;**[!UICONTROL 「熱門篩選]** > **[!UICONTROL 定義篩選」]**&#x200B;面板中的篩選相關資訊。

![熒幕擷圖顯示[定義篩選]對話方塊，其中包含依應用程式、使用者和專案篩選的選項。](/help/admin/admin/assets/filter.png)

下列表格會提供篩選的範例和相關資訊：

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 篩選 </th> 
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
   <td colname="col3"> <p>符合<span class="term"> a b c</span>和<span class="term"> b a c</span>，依此類推。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含任何字詞 </p> </td> 
   <td colname="col02"> <p>包含至少其中一個篩選器 (以空格分隔)。 </p> </td> 
   <td colname="col2"> <p>ABC </p> </td> 
   <td colname="col3"> <p>符合<span class="term"> A1</span>、<span class="term"> B2</span>、<span class="term"> C3</span>，但不符合<span class="term"> D4</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>包含片語 </p> </td> 
   <td colname="col02"> <p>包含搜尋篩選器，也可能包含其他詞語。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>符合<span class="term"> abc</span>和<span class="term"> abc def</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含任何字詞 </p> </td> 
   <td colname="col02"> <p>傳回不包含您輸入值的所有項目。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>符合<span class="term"> d e f</span>，但不符合<span class="term"> c d e f</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不包含此片語 </p> </td> 
   <td colname="col02"> <p>傳回不包含您片語的所有項目。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>排除<span class="term"> abc</span>、<span class="term"> abc def</span>，並符合<span class="term"> def</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>等於 </p> </td> 
   <td colname="col02"> <p>傳回完全相符的項目。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term">abc</span> 會是唯一傳回的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不等於 </p> </td> 
   <td colname="col02"> <p>傳回與您輸入的值不完全相符的所有項目。 </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>不符合<span class="term"> a</span>。 </p> <p>比對 <span class="term">a b c</span>。 </p> <p>比對 <span class="term">abc</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開始於 </p> </td> 
   <td colname="col02"> <p>傳回以特定值作為開頭的結果。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>符合<span class="term"> abcd</span>，但不符合<span class="term"> 1abc</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>終止於 </p> </td> 
   <td colname="col02"> <p>傳回以特定值作為結尾的結果。 </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>符合 <span class="term">Wxyz</span> 而非 <span class="term">wxyz0</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>進階 (特殊字元) </p> </td> 
   <td colname="col02"> <p>可讓您使用規則運算式字元： </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^Home*Page$" | sports </p> </td> 
   <td colname="col3"> <p> 這會定義一個篩選器，其開頭為<span class="term">首頁</span>，然後尋找零個或多個字元，最後以<span class="term">頁面</span>結束。 </p> <p>此外，也會尋找任何含有 <span class="term">sports</span> 的頁面。 </p> <p>以下是一些比對的範例： </p> 
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
   <td colname="col1"> 「 」 </td> 
   <td colname="col2"> 等於 </td> 
   <td colname="col3"> <p>除非未與另一個引號成對，否則不會予以逸出。例如，<span class="term"> 17" Display</span>不是片語。 </p> </td> 
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
   <td colname="col2"> Not </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> 或 </td> 
   <td colname="col3"> <p>僅在<span class="term">進階（特殊字元）</span>篩選器中支援。 </p> </td> 
  </tr> 
 </tbody> 
</table>

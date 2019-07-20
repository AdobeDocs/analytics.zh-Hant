---
description: 列設定依您拖放至表格中的元件而異。
seo-description: 列設定依您拖放至表格中的元件而異。
seo-title: 列設定
title: 列設定
uuid: f30c31d5-1fd4-4b93-94c3-ca441099 Fe2 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 列設定

列設定依您拖放至表格中的元件而異。

您也可以使用[表格中的按右鍵動作](../../../../analyze/analysis-workspace/visualizations/freeform-table.md#concept_0D2E24FCCBAF4194AA941448860E422F)來管理選取的列。

若要存取表格列設定，按一下維度、區段、量度、時段旁的設定圖示，或按以下各項之中的劃分:

![](assets/row-settings.png)

<table id="table_7ACE6413DB1F40349ED2860020F92E55"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 列設定 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="../../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> 日期比較</a> </p> </td> 
   <td colname="col2"> <p><b>對齊各欄日期，讓所有開始日期在同一列。</b> </p> <p>當您選擇對齊日期，例如，在 2016 年 10 月和 9 月的月對月比較中，左欄將從 10 月 1 日開始，右欄將從 9 月 1 日開始: </p> <p><img placement="break"  src="assets/add-time-period-column3.png" width="500px" id="image_99398B13FEDA4715B8B818DF6093CA37" /> </p> <p>預設為停用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>百分比 </p> </td> 
   <td colname="col2"> <p><b>依列計算百分比</b> </p> <p>強制自由格式表格跨列計算儲存格百分比，而非整欄計算。此設定在計算趨勢百分比時特別實用。使用<span class="uicontrol">「視覺化」</span>圖示時，此功能就會預設為啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>欄總計 </p> </td> 
   <td colname="col2"> <p>這些設定只會在<a href="../../../../analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md#concept_C50E7DFBC0504C72A973123192F487D8" format="dita" scope="local">手動 (靜態) 列</a>顯示 (當您已選取有限數目的項目)，不會在動態列顯示 (當您拖放會顯示所有項目的維度)。 <p>附註: 若是<i>量度</i>手動列，此設定會停用，因為去加總表格中目前列以外的任何量度不太合理。 </p> </p> <p><b>加總目前在每個欄中的值來計算總計 (預設為啟用):</b> </p> <p>這個選項只會計算目前在表格中的列。(用戶端計算) </p> <p><b>依據每個量度的所有列計算總計 (預設為停用):</b> </p> <p>這個選項包含此維度的所有維度項目，即使是未列於表格中的項目。(伺服器端計算) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>劃分 </p> </td> 
   <td colname="col2"> <p><b>依位置劃分:</b> </p> <p>您可以根據 Freeform 表格中的固定位置執行劃分。例如，您可以指定一律劃分前七列。 </p> <p>(之前，劃分中的值清單已「鎖定」。這會導致一種情況，例如，如果您<span class="term">日期</span> (依<span class="term">頁面</span>)，您會看到選定日期範圍內前 50 頁的清單。如果您儲存該報告，然後在一個月後執行，則前 50 頁可能已變更。然而，Analysis Workspace 會使用原始劃分的結果，並傳回相同的頁面，但以當前月份為日期範圍。) </p> <p>依固定位置執行劃分: </p> 
    <ol id="ol_A396A11566AA4F52BC3ABBC373CEF477"> 
     <li id="li_BDAB1E9A48D44944A4F7C31F1182B923">劃分表格中的一些列。 </li> 
     <li id="li_C5610437D3714CCEB9F3C771864B4336">按一下您要固定位置之表格列旁邊的設定 (齒輪) 圖示。 </li> 
     <li id="li_675E429DC3B94201978166F9408D30B1">核選「<span class="uicontrol">依位置劃分</span>」旁的核取方塊。 </li> 
     <li id="li_E8A417D0D6D1438CAE825843BA0A7060">變更排序順序或日期範圍，然後注意劃分現在已繫結至該列的位置，而不是程式碼寫定的列。 </li> 
    </ol> <p>預設為停用。 </p> </td> 
  </tr> 
 </tbody> 
</table>


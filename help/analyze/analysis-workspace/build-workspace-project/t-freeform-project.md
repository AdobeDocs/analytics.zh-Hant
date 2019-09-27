---
description: 建立專案並新增元件 (維度、量度、區段和日期範圍) 至自由面板。
keywords: Analysis Workspace
seo-description: 建立專案並新增元件 (維度、量度、區段和日期範圍) 至自由面板。
seo-title: 建立 Workspace 專案
solution: Analytics
title: 建立 Workspace 專案
topic: Reports and Analytics
uuid: c1def77a-a76e-4699-9feb-1ede5b70b7ba
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 建立 Workspace 專案

建立專案並新增元件 (維度、量度、區段和日期範圍) 至自由面板。

本文將帶您了解「Analysis Workspace」介面元素，並說明如何建立專案。如需特定使用案例，請參 [閱分析工作區的使用案例](../../../analyze/analysis-workspace/freeform-analysis-examples-use-cases.md#concept_173D1EB783F24EA89E754628BA30FF4B)。

## 建立專案

1. 指定建立和組織專案的使用者權限。

   在建立或組織 Analysis Workspace 專案前，管理員必須先將您新增至已啟用「**在 Analysis Workspace 中建立 / 組織專案**」權限的群組，或新增至「**[!UICONTROL 完全報表存取]」使用者群組。**( **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; [Groups](https://marketing.adobe.com/resources/help/en_US/reference/groups.html)).

1. In the [!DNL Experience Cloud], click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Workspace]**.

   ![](assets/analysis_workspace_menu.png)

   Alternatively, enter a forward slash (/) to open the report search bar, then type *`workspace`*.

   ![](assets/analysis-app-search.png)

1. Click **[!UICONTROL Create New Project]**.

   您可以選擇從以下來源建立專案

* 空白專案 (預設)。如需指示，請參閱以下內容。
* 標準範本。這些範本皆由 Adobe 建立且出廠即提供。如需指示，請參閱[範本](../../../analyze/analysis-workspace/build-workspace-project/starter-projects.md#concept_49B9A327C5004DB0A4BE6291435625C5)
* 自訂範本。這些範本是由擁有管理員權限的使用者所建立。如需指示，請參閱[範本](../../../analyze/analysis-workspace/build-workspace-project/starter-projects.md#concept_49B9A327C5004DB0A4BE6291435625C5)

   ![](assets/start_modal.png)

1. To create a project from a blank project, click **[!UICONTROL Blank Project]**.

   * Then click **[!UICONTROL Create]**, or
   * Simply click **[!UICONTROL Enter]**.
   接著會出現空白專案，其中顯示自由面板和資料表格視覺化。

   ![](assets/fa_project_new.png)

   >[!NOTE]
   >
   >有時，在載入專案（或切換至報表套裝）時會顯示「不相容的報表套裝」訊息，其中專案中包含的所有元件（量度／維度）並非都包含在報表套裝中。 您可以看到不相容的元件清單，得知收到這類訊息的原因。

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/analysis-workspace-components.md#concept_BEBE3A75E072495D9E2F895567BBD462" format="dita" scope="local"> 元件</a> </td> 
   <td colname="col2"> <p>您可以拖曳至專案的維度、量度、區段和日期範圍。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276" format="dita" scope="local"> 視覺效果</a> </td> 
   <td colname="col2"> <p>您可拖曳至介面的面板或專案區域的項目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/visualizations/freeform-table.md#concept_0D2E24FCCBAF4194AA941448860E422F" format="dita" scope="local"> 自由面板 </a> </td> 
   <td colname="col2"> <p>您與「Analysis Workspace」互動的畫布或工作區。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 儲存您的專案。Name the project, provide a description (optional, but useful) and tag the project (optional), then click **[!UICONTROL Save Project]**.

   ![](assets/save_project.png)

1. 您現在可按一下滑鼠右鍵複製視覺效果或面板，然後再將複製的元素貼到 (「插入」) 專案內的其他位置或其他專案中。

   您可使用這項功能建立「建置組塊」 (預先定義的視覺效果/面板) 並將這些組塊複製到其他專案中，然後藉由您業務專用的資料，更快地展開作業。

   >[!NOTE]
   >
   >複製／另存新檔後，內部連結現在會相對於其所在的專案，而非原始的專案。

## 新增元件與視覺效果 {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. 拖曳並拖曳至專案， *`components`* 以建 *`visualizations`* 立您的專案。

   **元件**

   元件工具列會顯示您最常使用的可搜尋維度、量度、區段和日期範圍。

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元件 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 維度 (橘色) </td> 
   <td colname="col2"> <p>在專案層級套用 </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>維度名稱後面附加了 Prop#、eVar# 和 event#，您可以依據這些編號來搜尋。範例:「內部促銷活動」會在左側欄中顯示為「內部促銷活動 (evar2)」。 </p> <p> 請注意，prop、eVar 和事件編號不會顯示在表格中 (以保持標題簡潔)。 </p> <p>在被拖曳至自由表格中、或是顯示在左側欄時，部分現有的維度會有預設的排序順序。例如，當「小時」被拖放到表格中，或顯示在左側欄時，會以從上午 12 點至下午 11 點的順序排序。您仍可以選擇依照任何量度欄來排序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度 (綠色) </td> 
   <td colname="col2"> <p>在專案層級套用。 </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term"> 發生次數</span> ，是資料表格的預設度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 區段 (藍色) </td> 
   <td colname="col2"> <p>僅可在面板層級拖曳，但您可在資料表格中建立內嵌區段。 </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>如需詳 <a href="../../../analyze/analysis-workspace/freeform-analysis-examples-use-cases.md#concept_173D1EB783F24EA89E754628BA30FF4B" format="dita" scope="local"> 細資訊，請參閱分析工作區的使用案例</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日期範圍和粒度 (紫色) </td> 
   <td colname="col2"> <p>僅可在面板層級拖曳。您可從日曆設定日期範圍以建立專案。 </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[視覺效果](../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276)**

「[!UICONTROL 視覺化]」面板提供標準的 Analytics 圖形、圖表、環圈圖、資料表格、[同類群組](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md#concept_9D240A490265427DA694D18D14EACC0E)表格、Venn 圖表等等。您可以拖放多個視覺化至專案。

![步驟結果](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. 步驟

## 使用滑鼠右鍵功能表可自訂您的資料 {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

滑鼠右鍵功能表可讓您執行下列動作，視您在表格中按下滑鼠右鍵的儲存格而定。

![步驟結果](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 動作 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> 新增時段欄</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764" format="dita" scope="local"> 比較時段</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複製至剪貼簿 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除選取 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md" format="dita" scope="local"> 從選取範圍建立警報</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md#task_B594DA2476E84DFDA8279E831F0BD9C4" format="dita" scope="local"> 劃分</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">維度 </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">量度 </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">區段 </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">時間 </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276" format="dita" scope="local"> 視覺化</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/curate-share/download-send.md#concept_BB548979F47F45739679B830428C3025" format="dita" scope="local"> 下載為 CSV</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/analysis-workspace-features.md#concept_4D69EE46E3C24EEB97C935A8789364F9" format="dita" scope="local"> 趨勢選取範圍</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/components/t-freeform-project-segment.md#task_11C6A2C7717B48049E5750B9D20FEC80" format="dita" scope="local"> 從選取範圍建立區段</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md#concept_74FAC1C6D0204F9190A110B0D9005793" format="dita" scope="local"> 在區段比較中執行</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 僅顯示選取的列 </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顯示所有列 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

請參閱 [Analysis Workspace 可用的鍵盤和滑鼠互動](../../../analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md#concept_9A6356084DBC4D468E265E7A65B3E051)，以獲得複製和選取行的相關資訊。

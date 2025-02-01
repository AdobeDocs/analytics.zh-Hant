---
title: 區段比較面板概述
description: 瞭解如何使用 Analysis Workspace 中區段 IQ 的區段比較面板。
keywords: Analysis Workspace, 區段 IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 37%

---

# 區段比較面板概述 {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="區段比較"
>abstract="快速比較所有資料點的兩個區段，以自動找到相關的差異。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="區段比較面板"
>abstract="快速比較所有資料點的兩個區段，以自動找到相關的差異。<br/><br/>**參數&#x200B;**<br/>**新增區段**：您要分析的第一個區段。<br/>**比較依據**：您要比較的第二個區段。這將自動填入&#x200B;*其他所有人*，這是您第一個區段的反函數。如果需要，您可以用不同的區段來取代這個。<br/>**進階設定**：在區段比較中排除元件被分析的能力。"
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文會在_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中記錄區段比較面板。_<br/>_在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中沒有對應的面板。_

>[!ENDSHADEBOX]

「區段比較」面板是[「區段 IQ」](../../segment-iq.md)中的工具，可從不限數量的區段中找出統計數據上最顯著的差異。此功能會針對您存取的所有維度和量度進行反覆自動分析。它會從提升公司 KPI 的客群細分群體當中找出關鍵特性，讓您查看任何細分群體重疊的程度。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [區段比較](https://video.tv.adobe.com/v/23976?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]



## 使用

若要使用&#x200B;**[!UICONTROL 歸因]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 歸因]**&#x200B;面板。 有關如何建立面板的資訊，請參閱[建立面板](../panels.md#create-a-panel)。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。



### 面板輸入

您可以使用下列輸入設定來設定[!UICONTROL 區段比較]面板：

![區段比較輸入面板](assets/segment-comparison-input.png)

| 輸入 | 說明 |
| --- | --- |
| **[!UICONTROL 新增區段]** | 選取您要比較的維度。 |
| **[!UICONTROL 與]**&#x200B;比較 | 選取您要用來比較初始選取區段的維度。 如果您未選取特定區段，則會使用預設區段&#x200B;**[!UICONTROL 其他所有人]**。 |
| **[!UICONTROL 顯示/隱藏進階設定]** | 選取[顯示]進階設定&#x200B;]**以設定**[!UICONTROL &#x200B;排除的元件&#x200B;]**，選取[隱藏]進階設定]**&#x200B;以隱藏&#x200B;**[!UICONTROL 排除的元件]**。**[!UICONTROL **[!UICONTROL  |
| **[!UICONTROL 排除的元件]** | 您可以指定的元件，例如&#x200B;**[!UICONTROL Dimension]**、**[!UICONTROL 量度]**&#x200B;或排除的&#x200B;**[!UICONTROL 區段]**。<br><ul><li>從容器拖放一或多個維度、量度或區段至&#x200B;**[!UICONTROL 排除的元件]**&#x200B;容器。</li><li>若要移除元件，請選取型別(**[!UICONTROL Dimension]** **[!UICONTROL 量度]**，或&#x200B;**[!UICONTROL 區段]**)，然後選取![交叉大小75](/help/assets/icons/CrossSize75.svg)以移除元件。 若要移除所有元件，請選取&#x200B;**[!UICONTROL 全部清除]**。</li><li>若要將目前選擇的維度、量度和區段設定為預設值，請選取「**[!UICONTROL 設定為預設值]**」。</li></ul> |

選取&#x200B;**[!UICONTROL 建置]**&#x200B;以建置面板。

### 面板輸出

Adobe Analytics分析完所需的兩個區段後，輸出面板會透過數個視覺效果顯示結果：

![面板輸出區段比較](assets/segment-comparison-output.png)

| 視覺效果 | 說明 |
|---|---|
| **[!UICONTROL 大小和重疊]** | 以[Venn](/help/analyze/analysis-workspace/visualizations/venn.md)視覺效果說明每個所選區段的比較大小以及彼此重疊的程度。 |
| 第1個區段的&#x200B;**[!UICONTROL 不重複訪客]** | 顯示第一個區段不重複訪客的[摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)視覺效果（在單頁造訪範例中） |
| 第2個區段的&#x200B;**[!UICONTROL 不重複訪客]** | 顯示第二個區段不重複訪客的[摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)視覺效果（在第一次瀏覽的範例中） |
| 針對區段&#x200B;**[!UICONTROL 排名在前的量度]** | 顯示所選區段排名最前之量度的[自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 |
| **[!UICONTROL 一段時間內的量度（依區段）]** | 顯示所選區段量度隨時間變化的[線](/help/analyze/analysis-workspace/visualizations/line.md)視覺效果。 |
| 針對區段&#x200B;**[!UICONTROL 排名在前的維度專案]** | [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)顯示所選區段的混合維度專案。 |
| **[!UICONTROL 依區段Dimension專案]** | [橫條圖](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)視覺效果會依區段顯示維度專案。 |
| 針對區段&#x200B;**[!UICONTROL 排名最前的區段]** | [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)會針對區段顯示排名最前的區段。 |
| **[!UICONTROL 區段重疊]** | 顯示區段重疊的[Venn](/help/analyze/analysis-workspace/visualizations/venn.md)視覺效果。 |

使用![編輯](/help/assets/icons/Edit.svg)來重新設定及重建面板。


<!--
#### Size and overlap

Illustrates the comparative sizes of each selected segment and how much they overlap with each other using a venn diagram. You can hover over the visual to see how many visitors were in each overlapping or non-overlapping section. You can also right click on the overlap to create a brand new segment for further analysis. If the two segments are mutually exclusive, no overlap is shown between the two circles (typically seen with segments using a hit container).

![Size and overlap](assets/size-overlap.png)

#### Population summaries

To the right of the Size and Overlap visualization, the total unique visitor count in each segment and overlap is shown.

![Population summaries](assets/population_summaries.png)

#### Top metrics

Displays the most statistically significant metrics between the two segments. Each row in this table represents a differentiating metric, ranked by how different it is between each segment. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific metric is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific metric. If a metric is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Metrics added to this table after the segment comparison has finished do not receive a Difference Score.

![Top metrics](assets/top-metrics.png)

#### Metric over time by segment

To the right of the metrics table is a linked visualization. You can click a line item in the table on the left, and this visualization updates to show that metric trended over time.

![Top metrics line](assets/linked-viz.png)

#### Top dimensions

Shows the most statistically significant dimension items across all of your dimensions. Each row shows the percentage of each segment exhibiting this dimension item. For example, this table might reveal that 100% of visitors in 'Segment A' had the dimension item 'Browser Type: Google', whereas only 19.6% of 'Segment B' had this dimension item. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific dimension item is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific dimension item. If a dimension item is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Dimension items added to this table after the segment comparison has finished do not receive a Difference Score.

![Top dimensions](assets/top-dimension-item1.png)

#### Dimension items by segment

To the right of the dimensions table is a linked bar chart visualization. It shows all displayed dimension items in a bar chart. Clicking a line item in the table on the left updates the visualization on the right.

![Top dimensions bar chart](assets/top-dimension-item.png)

#### Top segments

Shows which other segments (other than the two segments selected for comparison) have statistically significant overlap. For example, this table can show that a third segment, 'Repeat Visitors', overlaps highly with 'Segment A' but does not overlap with 'Segment B'. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific segment is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific segment. If a segment is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Segments added to this table after the segment comparison has finished do not receive a Difference Score.

![Top segments](assets/top-segments.png)

#### Segment overlap

To the right of the segments table is a linked venn diagram visualization. It shows the most statistically significant segment applied to your compared segments. For example, 'Segment A' + 'Statistically significant segment' vs. 'Segment B' + 'Statistically significant segment'. Clicking a segment line item in the table on the left updates the venn diagram on the right.

![Top segments venn diagram](assets/segment-overlap.png)

-->

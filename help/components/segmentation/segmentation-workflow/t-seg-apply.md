---
description: 如何將區段用於報表。
title: 使用區段
feature: Segmentation
role: User
exl-id: 870026e2-a3a3-4d87-a6c2-6189098d3676
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# 使用區段

若要跨Analysis Workspace使用區段，您只要從元件邊欄中的&#x200B;**[!UICONTROL 區段]**&#x200B;拖曳一或多個區段並放置在上方即可：

* Analysis Workspace中的[面板](/help/analyze/analysis-workspace/c-panels/panels.md)可劃分面板中的所有視覺效果。
* Analysis Workspace中[自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)的標題列會取代維度。
* Analysis Workspace中[自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)中的一列，用以起始劃分。
* Analysis Workspace中[自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)中的資料行，用來新增或取代資料行，或起始篩選器。
* 設定允許放置區段的視覺效果面板或面板。 例如，在[區段比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)面板中，或[關鍵量度](/help/analyze/analysis-workspace/visualizations/key-metric.md)摘要視覺效果中
* 區段](/help/components/segmentation/segmentation-workflow/seg-build.md#definition-builder)的[定義產生器，因此您在區段定義中包含區段。
* 計算量度的[定義產生器](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#definition-builder)，因此您在計算量度定義中包含區段。

<!--
How to apply one or more segments to a report from the segment rail.

1. Bring up the report to which you want to apply a segment, for example the [!UICONTROL Pages Report].
1. Click **[!UICONTROL Show Segments]** above the report. The segment rail opens.

   ![](assets/segment_rail.png)

1. Mark the checkbox next to one or more of the segments or **[!UICONTROL Search Segments]** to find the right segment.

   >[!NOTE]
   >
   >You can apply more than one segment to a report (this is called segment stacking). When multiple segments are applied, the criteria in each segment is combined using an 'and' operator and then applied. There is no limit to how many segments you can stack.

   >[!NOTE]
   >
   >Clicking the Information icon (i) next to the segment name lets you preview the key metrics to see whether you have a valid segment and how broad the segment is.

1. You can filter by report suite by selecting the **[!UICONTROL (Only) `<report suite name>`]** check box. This will show only those segments that were last saved in that report suite.
1. Click **[!UICONTROL Apply Segment]** and the report will refresh. The segment or segments that are applied now display at the top of the report:

   ![](assets/applied_segments.png)

-->

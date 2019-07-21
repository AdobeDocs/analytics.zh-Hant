---
description: 'null'
seo-description: 'null'
seo-title: 執行貢獻分析
title: 執行貢獻分析
uuid: 5282a5f9-0771-4974-93cb-335204bde114
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# 執行貢獻分析

「貢獻分析」是密集型機器學習程序，專門設計來找出 Adobe Analytics 中所觀察到異常值的貢獻者。目的是要協助使用者比以往更快找出重點區域或機會以便進行其他分析。

## 執行貢獻分析 {#section_7D2C5E48A5664727941DF4C90976D9DC}

在專案中叫用貢獻分析有兩個分法:

* In a freeform table with daily granularity, right-click any row and select **[!UICONTROL Run Contribution Analysis]**. 您甚至可以在未顯示異常的列上執行貢獻分析。

   >[!NOTE]
   >
   >我們目前僅支援每日詳細程度的貢獻分析。

   ![](assets/run_ca.png)

* 在折線圖中，將滑鼠移至折線圖中異常資料點的上方。按一下出現的「**[!UICONTROL 分析]」連結。**

   ![](assets/contribution-analysis.png)

1. (選擇性) 在線性圖或表格中按一下&#x200B;**[!UICONTROL 「執行貢獻分析」]**&#x200B;後，您可藉由[排除維度](../../../../analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md#section_F6932F4BF74544B5872164E7B1E0C6FC)來縮小分析範圍 (並加快分析速度)。

1. 等候貢獻分析載入。取決於您報表套裝的大小以及維度數目，這可能需要相當長的時間。貢獻分析會對每個維度的前 50,000 個項目執行分析。
1. Analysis Workspace 隨後會在此專案內直接載入新的「貢獻分析」面板。如果您曾在「Reports &amp; Analytics」中使用過「貢獻分析」，您會發現很多面板都很熟悉:

   * 顯示當天「**造訪**」數的視覺效果。
   * 上下文的每月「**造訪趨勢線**」。
   * 造成此異常的「**排名最前的項目**」(依據[貢獻積分](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_contribution_score.html)排序)，加上相關量度，以及「獨特訪客」量度，以從規模觀點來將量度放在上下文中。

   * 「[產生的區段](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_workflow_premium.html)」(排名最前的項目叢集) 表格會根據「貢獻積分」、異常發生次數以及對異常量度的貢獻整體百分比來識別關聯。接著系統將此擷取為對象區段 (貢獻區段 1、貢獻區段 2 等)。按一下「i」(資訊) 按鈕可讓您檢視每個自動區段的定義，包括組成其的排名最前的項目:

      ![](assets/auto_segment.png)

1. 由於貢獻分析現在是 Analysis Workspace 的一部分，因此您可以從表格的右鍵功能表運用它的多個功能，讓您的分析結果更具意義，例如:

   * [依據另一個維度劃分每個維度項目。](../../../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md#task_B594DA2476E84DFDA8279E831F0BD9C4)
   * [顯示一或多列的趨勢。](../../../../analyze/analysis-workspace/analysis-workspace-features.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [新增視覺效果。](../../../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276)
   * [建立警報。](/help/components/c-alerts/intellligent-alerts.md)
   * [建立或比較區段。](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md#concept_74FAC1C6D0204F9190A110B0D9005793)

>[!NOTE]
>
>我們會在貢獻分析和連結到它的智慧提醒專案中，強調分析異常的異常。如此即可以更清楚的方式指明分析所得的異常項目。

## Exclude dimensions from Contribution Analysis {#section_F6932F4BF74544B5872164E7B1E0C6FC}

有時候，您可能會想要從「貢獻分析」排除部分維度。例如，您可能不在意任何與瀏覽器或硬體相關的維度，因此希望藉由移除這些項目來加快分析速度。

1. 在您按一下&#x200B;**[!UICONTROL 「執行貢獻分析」]**(或線性圖中的&#x200B;**[!UICONTROL 「分析」]) 後，**「排除的維度」]面板隨即顯示。**[!UICONTROL **

1. Just drag any unwanted dimensions into the **[!UICONTROL Excluded Dimensions]** panel, then save the list by clicking **[!UICONTROL Set as Default]**. 或者，按一下&#x200B;**[!UICONTROL 「全部清除」]，然後選取要排除的維度從頭來過。**

   ![](assets/exclude_dimensions.png)

1. 新增要排除的維度後 (或選擇不要排除)，按一下&#x200B;**[!UICONTROL 「執行貢獻分析」]。**
1. 若您需要修訂排除的維度的清單，可以在「維度」上連按兩下，排除的維度的清單隨即顯示:

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.


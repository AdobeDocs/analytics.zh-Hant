---
description: 瞭解如何在Analysis Workspace中執行貢獻分析報表。
title: 執行貢獻分析
role: User, Admin
exl-id: 20d1ba8d-3e4e-4702-ae28-5eb6bf00847b
feature: Anomaly Detection
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 14%

---

# 執行貢獻分析

[「貢獻分析」是密集型機器學習程序，專門設計來找出 Adobe Analytics 中所觀察到異常值的貢獻者。](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)目的是要協助使用者比以往更快找出重點區域或機會以便進行其他分析。

>[!NOTE]
>
>貢獻分析僅支援具有每日粒度的資料。

執行貢獻分析的步驟如下：

1. 在專案中叫用貢獻分析。

   ![執行貢獻分析](assets/run-contribution-analysis.png)

   1. 線上條視覺效果中，根據具有每日粒度的自由表格，選取異常資料點。 從快顯視窗中選取&#x200B;**[!UICONTROL 分析]**。
   1. 在設有每日粒度的自由表格中，從任何列上的內容功能表選取&#x200B;**[!UICONTROL 執行貢獻分析]**。 您甚至可以對未顯示任何異常的列執行分析。
   1. 在設有每日粒度的自由表格中，在指出異常的列上：
      1. 選取指標◥。
      1. 從![警示](/help/assets/icons/Alert.svg) **[!UICONTROL 偵測到的異常]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 開啟貢獻分析]**。



1. （選擇性）您可以縮小分析範圍（因此可加快分析速度） [排除維度](#exclude-dimensions)。

   ![排除貢獻分析中的維度](assets/excluding-dimensions.png)

1. 選取&#x200B;**[!UICONTROL 執行貢獻分析]**。

1. 正在處理貢獻分析，請稍候。 處理作業可能需要相當長的時間，視報表套裝大小和維度數量而定。 貢獻分析會針對每個維度的前50,000個專案執行分析。 您也會收到有關剩餘[個貢獻分析Token](anomaly-detection.md#contribution-analysis-tokens)的通知。

   ![貢獻分析正在執行](assets/contribution-analysis-executing.png)

1. Analysis Workspace直接在此專案中載入新的&#x200B;**[!UICONTROL 貢獻分析]**&#x200B;面板。

   ![貢獻分析面板](assets/contribution-analysis.png)

   * [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)視覺效果。
   * 每月趨勢[線](/help/analyze/analysis-workspace/visualizations/line.md)視覺效果。
   * 顯示哪些排名最前的專案造成此異常的&#x200B;**[!UICONTROL 排名最前的專案]** [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)，依[貢獻分數](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)排序。 其他欄會顯示相關量度，以及提供內容的&#x200B;**[!UICONTROL 不重複訪客]**&#x200B;量度。

   * **[!UICONTROL 產生的區段（最上層專案叢集）]** [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)會根據貢獻分數、異常發生次數和導致異常數度的整體百分比，識別最上層專案的關聯。 然後，此關聯會被擷取為對象區段（「貢獻區段1」、「貢獻區段2」等）。 選取![資訊](/help/assets/icons/Info.svg)以顯示區段的定義，包括區段由哪些排名最前的專案組成：


1. 由於貢獻分析現在是Analysis Workspace的一部分，因此您可以從自由格式表格快顯選單中運用它的多個功能，讓您的分析更具意義，例如：

   * [依其他維度劃分每個維度專案](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)
   * [顯示一或多個資料列的趨勢](/help/analyze/analysis-workspace/home.md#section_34930C967C104C2B9092BA8DCF2BF81A)
   * [新增視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)
   * [建立警示](/help/components/alerts/alerts-overview.md)
   * [建立或比較區段。](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

>[!NOTE]
>
>分析的異常在「貢獻分析」及與其連結的「智慧型警報」專案中以藍點標示。 此醒目提示可提供所分析異常的更清楚指示。


## 排除維度

您可能會想要從「貢獻分析」中排除一些維度。 例如，您可能不在意任何與瀏覽器或硬體相關的維度，因此希望藉由移除這些項目來加快分析速度。

若要管理排除的維度：

* 將任何不想要的維度拖曳至&#x200B;**[!UICONTROL 排除的維度]**&#x200B;面板，然後按一下&#x200B;**[!UICONTROL 設定為預設]**&#x200B;以儲存清單。

* 選取&#x200B;**[!UICONTROL 全部清除]**&#x200B;以重新開始。

* 選取![維度](/help/assets/icons/Dimensions.svg)以顯示內容功能表，並使用![CrossSize400](/help/assets/icons/CrossSize400.svg)從清單中移除任何選取的排除維度。

  ![](assets/excluded-dimensions-list.png)

修改要排除的維度後，請再次選取&#x200B;**[!UICONTROL 執行貢獻分析]**。


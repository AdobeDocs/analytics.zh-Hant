---
description: 在分析工作區中建立同類群組並執行同類群組分析報表。
keywords: Analysis Workspace
seo-description: 在分析工作區中建立同類群組並執行同類群組分析報表。
seo-title: 執行同類群組分析報表
solution: Analytics
title: 執行同類群組分析報表
topic: Reports & Analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960 ff0 bb4
translation-type: tm+mt
source-git-commit: be8d889e03479cfb1926e7a82112964635cd2545

---


# 設定同類群組分析報表

在分析工作區中建立同類群組並執行同類群組分析報表。

1. In Analysis Workspace, click the **[!UICONTROL Visualizations]** icon in the left rail and drag a **[!UICONTROL Cohort Table]** to the canvas.

   ![](assets/cohort-table.png)

1. Define the **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]**, and **[!UICONTROL Settings]** as defined in the table below.

| 元素 | 說明 |
|--- |--- |
| **[!UICONTROL 包含條件]** | 您可以套用最多 10 個包含區段和最多 3 個包含量度。此度量可指定將使用者放入同類群組的項目。例如，如果包含量度是「訂購」，則只有在同類群組分析的時間範圍內下訂單的使用者，才會包含在初始同類群組中。<br>量度間的預設運算子為「和」，但您可以將其變更為「或」。此外，您也可以為這些量度新增數值篩選條件。例如:「造訪 &gt;= 1」。</br> |
| **[!UICONTROL 回訪標準]** | 您可以套用最多 10 個回訪區段和最多 3 個回訪量度。該量度指出已保留使用者 (保留率) 或未保留使用者 (流失率)。例如，如果回訪量度是「視訊檢視」，則只有在後續時段 (在將使用者新增至同類群組後) 檢視視訊的使用者，才會表示為保留。可以量化保留的另一個量度是「造訪」。 |
| **[!UICONTROL 詳細程度]** | 日、週、月、季或年的時間粒度。 |
| **[!UICONTROL 類型]** | ****&#x200B;保留率 (預設): 保留率同類群組會衡量一段時間中，訪客同類群組回訪您網站的程度。這是我們一直以來都有的標準同類群組，其代表回訪和重複的使用者行為。「保留率同類群組」在表格中以綠色表示。<br>**[!UICONTROL 流失]**：流失(也稱為「attrition」或「流失」)同類群組會測量您的訪客群組在一段時間內流失的情形。流失率 = 1 - 保留率。流失率會向您顯示客戶未回訪的頻率，非常適合用來衡量黏著度及商機。您可以使用流失分析並識別焦點區域：哪些群組區段可供您注意。A Churn Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL 設定]** | **[!UICONTROL 滾動式計算]**: 根據上一欄計算保留率或流失率，而非根據「包含」欄 (預設)。「滾動式計算」會變更「回訪」期間的計算方法。正常的計算方法會單獨找出符合「回訪」標準，且屬於包含期間的使用者，無論他們是否在先前期間的同類群組中。相反地，「滾動式計算」會找出符合「回訪」標準，且屬於先前期間的使用者。因此，「滾動式計算」會篩選並彙集在各期間持續滿足「回訪」標準的使用者。回訪標準會套用至所選期間之前的各個期間。</br><br>**[!UICONTROL 延時表格]**: 延時表格會衡量包含事件發生前後的經過時間。「延時表格」非常適合用於事前/事後分析。例如，若您有即將推出的產品或促銷活動，且您想追蹤執行前後的使用者行為並查看成效，則延時表格會並排顯示事前和事後的使用者行為，讓您瞭解直接的影響。「延時表格」中的包含前儲存格，是根據在包含期間符合「包含」條件，且在包含期間前符合「回訪」標準的使用者來計算。請注意，無法同時使用「延時表格」和「自訂維度同類群組」。</br><br>**[!UICONTROL 自訂維度同類群組]**: 根據選取的維度建立同類群組，而非根據以時間為主的同類群組 (預設)。許多客戶希望能透過時間以外的其他方法分析其同類群組，而新的「自訂維度同類群組」功能，可靈活地根據客戶選擇的維度建立同類群組。使用行銷管道、促銷活動、產品、頁面、地區等 Adobe Analytics 維度，說明保留率根據不同維度值的變化。「自訂同類群組維度」區段定義只會在屬於包含期間時套用維度項目，不會在屬於回訪定義時套用。</br><br>選擇「自訂維度同類群組」選項後，您可以將任何需要的維度拖放至拖放區域。這可讓您比較同一時段中類似的維度項目。例如，您可以並排比較城市、產品和促銷活動等的表現。它會傳回您的前 14 個維度項目。不過，您可以使用篩選器 (將游標停留在拖曳的維度右方即可使用)，僅顯示需要的維度項目。「自訂維度同類群組」無法與「延時表格」功能搭配使用。</br> |

1. Adjust the **[!UICONTROL Cohort Table Settings]** by clicking the gear icon.

|設定|說明|
|僅顯示百分比|移除數字值，只顯示百分比。|
|四捨五入至最接近的整數|將百分比值四捨五入至最接近的整數，而非顯示小數值。|
|顯示平均百分比列|在表格上方插入新列，然後新增每個欄內值的平均值。|

## 建立同類群組分析報表

1. Click **[!UICONTROL Build]**.

   ![步驟結果](assets/cohort-report.png)

   The report shows visitors who placed an order ( *`Included`* column), and who returned to your site in subsequent visits. 隨時間減少的造訪次數可讓您找出問題並採取行動。
1. (可選) 從選取範圍建立區段。

   Select cells (contiguous or noncontiguous), then right-click &gt; **[!UICONTROL Create Segment From Selection]**.

1. In the [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_build), further edit the segment, then click **[!UICONTROL Save]**.

   已儲存的區段即可用於 Analysis Workspace 的[!UICONTROL 區段]面板。
1. 命名同類群組專案，將其儲存。
1. (Optional) [Curate and share](../../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6) the project components.

   >[!NOTE]
   >
   >您必須先儲存專案，才能組織可用。


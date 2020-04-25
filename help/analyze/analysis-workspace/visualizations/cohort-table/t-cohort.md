---
description: 在 Analysis Workspace 中建立同類群組並執行同類群組分析報表。
keywords: Analysis Workspace
title: 執行同類群組分析報表
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 設定同類群組分析報表

在 Analysis Workspace 中建立同類群組並執行同類群組分析報表。

1. In Analysis Workspace, click the **[!UICONTROL Visualizations]** icon in the left rail and drag a **[!UICONTROL Cohort Table]** to the canvas.

   ![](assets/cohort-table.png)

1. 定義 **[!UICONTROL Inclusion Criteria]**、 **[!UICONTROL Return Criteria]**、 **[!UICONTROL Cohort Type]**&#x200B;和 **[!UICONTROL Settings]** 如下表中定義。

| 元素 | 說明 |
|--- |--- |
| **[!UICONTROL Inclusion Criteria]** | 您可以套用最多 10 個包含區段和最多 3 個包含量度。量度會指定將使用者放入同類群組的條件。例如，如果包含量度是「訂購」，則只有在同類群組分析的時間範圍內下訂單的使用者，才會包含在初始同類群組中。<br>量度間的預設運算子為「和」，但您可以將其變更為「或」。此外，您也可以為這些量度新增數值篩選條件。例如：「造訪 >= 1」。</br> |
| **[!UICONTROL Return Criteria]** | 您可以套用最多 10 個回訪區段和最多 3 個回訪量度。該量度指出已保留使用者 (保留率) 或未保留使用者 (流失率)。例如，如果回訪量度是「視訊檢視」，則只有在後續時段 (在將使用者新增至同類群組後) 檢視視訊的使用者，才會表示為保留。可以量化保留的另一個量度是「造訪」。 |
| **[!UICONTROL Granularity]** | 日、週、月、季或年的時間粒度。 |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]**（預設值）:保留群組會測量訪客群體在一段時間內回訪您屬性的程度。 這是我們一直以來都有的標準同類群組，其代表回訪和重複的使用者行為。「保留率同類群組」在表格中以綠色表示。<br>**[!UICONTROL Churn]**:流失（也稱為「流失」或「流失」）群組會測量訪客群體隨時間流逝而流失的情況。 流失率 = 1 - 保留率。流失率會向您顯示客戶未回訪的頻率，非常適合用來衡量黏著度及商機。您可以使用流失率來分析並找出重點區域，了解可能需要關注哪些同類群組區段。A Churn Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]**:根據上一欄而非「已包含」欄（預設值）來計算保留率或流失率。 「滾動式計算」會變更「回訪」期間的計算方法。正常的計算方法會單獨找出符合「回訪」標準，且屬於包含期間的使用者，無論他們是否在先前期間的同類群組中。相反地，「滾動式計算」會找出符合「回訪」標準，且屬於先前期間的使用者。因此，「滾動式計算」會篩選並彙集在各期間持續滿足「回訪」標準的使用者。回訪標準會套用至所選期間之前的各個期間。</br><br>**[!UICONTROL Latency Table]**:延遲表格會測量包含事件發生前後經過的時間。 「延時表格」非常適合用於事前/事後分析。例如，若您有即將推出的產品或促銷活動，且您想追蹤執行前後的使用者行為並查看成效，則延時表格會並排顯示事前和事後的使用者行為，讓您了解直接的影響。「延時表格」中的包含前儲存格，是根據在包含期間符合「包含」條件，且在包含期間前符合「回訪」標準的使用者來計算。請注意，無法同時使用「延時表格」和「自訂維度同類群組」。</br><br>**[!UICONTROL Custom Dimension Cohort]**:根據選取的維度建立群組，而非基於時間的群組（預設值）。 許多客戶希望能透過時間以外的其他方法分析其同類群組，而新的「自訂維度同類群組」功能，可靈活地根據客戶選擇的維度建立同類群組。使用行銷管道、促銷活動、產品、頁面、地區等 Adobe Analytics 維度，說明保留率在不同維度值的變化。「自訂同類群組維度」區段定義只會在屬於包含期間時套用維度項目，不會在屬於回訪定義時套用。</br><br>選擇「自訂維度同類群組」選項後，您可以將任何需要的維度拖放至拖放區域。這可讓您比較同一時段中類似的維度項目。例如，您可以並排比較城市、產品和促銷活動等的表現。它會傳回您的前 14 個維度項目。不過，您可以使用篩選器 (將游標停留在拖曳的維度右方即可使用)，僅顯示需要的維度項目。「自訂維度同類群組」無法與「延時表格」功能搭配使用。</br> |

1. 按一下齒 **[!UICONTROL Cohort Table Settings]** 輪表徵圖調整。

| 設定 | 說明 |
| 僅顯示百分比 | 移除數值並僅顯示百分比。|
| 將百分比四捨五入為最接近的整數 | 將百分比值四捨五入為最接近的整數，不顯示顯小數點後的值。|
| 顯示平均百分比列 | 在表格頂端插入新列，然後在每個欄中加入平均值。|

## 建立同類群組分析報表

1. 按一下 **[!UICONTROL Build]**.

   ![步驟結果](assets/cohort-report.png)

   報表會顯示下過訂單 ( *`Included`* 欄) 的訪客，以及在後續的造訪中回訪您網站的訪客。隨時間減少的造訪次數可讓您找出問題並採取行動。
1. (選用) 從選取項目建立區段。

   選取儲存格（連續或非連續），然後按一下滑鼠右鍵> **[!UICONTROL Create Segment From Selection]**。

1. In the [Segment Builder](https://marketing.adobe.com/resources/help/zh_TW/analytics/segment/seg_build.html), further edit the segment, then click **[!UICONTROL Save]**.

   The saved segment is available for use in the [!UICONTROL Segment] panel in Analysis Workspace.
1. 命名同類群組專案，將其儲存。
1. (選用) [組織與共用](/help/analyze/analysis-workspace/curate-share/curate.md)專案元件。

   >[!NOTE]
   >
   >您必須先儲存專案，才能進行組織。


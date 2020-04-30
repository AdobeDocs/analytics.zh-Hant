---
description: 設定即時報表的管理步驟。
title: 設定即時報表
topic: Admin tools
uuid: a2c3c515-55f2-4c64-ac92-a86d75e78a86
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# 設定即時報表

設定即時報表的管理步驟。

在 [!UICONTROL Reports & Analytics] 中設定即時報表，包括選取報表套裝，以及為其選取最多 3 個報表。

1. 選取您要啟用即時報告的報表套裝。

   導覽至 **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL View All Reports > Site Metrics]****[!UICONTROL Real-Time]** >並從上方的下拉式清單中選取報表套裝：

   ![](assets/report_suite_selector.png)

   如果您嘗試對尚未設定即時報表的報表套裝檢視即時報表，會出現一則訊息，供您設定報表套裝。

   ![](assets/rep_suite_not_set_up.png)

1. 按一下 **[!UICONTROL Configure]** （齒輪表徵圖）運行 [!UICONTROL Report Suite Manager]。

   (也可在 **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** >下 **[!UICONTROL Real-Time]**&#x200B;取得)

1. 開啟設 **[!UICONTROL Enable Real-Time]** 定。
1. 設定最多 3 個報告的即時資料收集，每個報告各一個量度和三個維度或分類。

   ![](assets/real_time_admin.png)

   如需深入瞭解支援的即時量度和維度，請參閱[支援的量度和維度](/help/components/c-real-time-reporting/realtime-metrics.md)。

   如果您已定義分類，則會以縮排顯示在其所定義的維度下方：

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >針對單一即時報表，目前不支援啟用重複維度，即使為每個維度選取了不同的分類亦同。

   如需分類的詳細資訊，請參閱[關於分類](/help/components/c-classifications2/c-classifications.md)。

   >[!NOTE]
   >
   >在「即時」中，有些維度 (如「搜尋關鍵字」或「產品」) 不會像在 Adobe Analytics 中的其他位置一樣持續存在。選取非持續性的量度時，會出現此警告：

   ![](assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   初始設定報告後，最多可能需要 20 分鐘，才會開始串流資料。從那時起，資料就立即可用。如需檢視即時報告的詳細資訊，請參閱[執行即時報告](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/t-running-report-types.html)。

1. 依預設，所有使用者都能存取即時報告。

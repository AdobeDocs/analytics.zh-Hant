---
description: 說明將篩選條件套用至流失報表的步驟。
title: 使用請求精靈篩選路徑流失報表
topic: Report builder
uuid: 269e900e-23bd-48d8-9bac-69e3167a9c18
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用請求精靈篩選路徑流失報表

說明將篩選條件套用至流失報表的步驟。

此範例顯示「頁面流失」報表。

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. 選擇正確的報表套裝。
1. 在左側的樹視圖中，選擇 **[!UICONTROL Paths]** > **[!UICONTROL Page]** > **[!UICONTROL Page Fallout]**。

   ![](assets/page_fallout.png)

1. 設定適當的[日期範圍](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)。
1. 按一下 **[!UICONTROL Next]**.
1. 在精靈的步驟2中，按一 **[!UICONTROL Row Labels]**&#x200B;下連結 **[!UICONTROL Define Checkpoints]** 。 (在流失報表中，您永遠必須定義路徑元素，這點與路徑報表已預先套用模式不同)。

   ![](assets/define_checkpoints.png)

1. 選取 **[!UICONTROL Filter]** 選項。

1. 在對話 **[!UICONTROL Define Site Section Fallout Checkpoints]** 方塊中，從儲存格範圍或清單中定義查核點。 然後按一下 **[!UICONTROL OK]**。
1. 決定要從儲存格範圍或清單選取。
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. 您可以定義 3 到 8 個查核點(Search for available elements by clicking **[!UICONTROL More]**.)

   如需縮小篩選範圍的詳細資訊，請參閱[篩選維度](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md)。1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. 按三 **[!UICONTROL OK]** 下，然後按一下 **[!UICONTROL Finish]**。

   報表應該會立即重新整理。

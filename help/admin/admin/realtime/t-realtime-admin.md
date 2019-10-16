---
description: 設定即時報表的管理步驟。
seo-description: 設定即時報表的管理步驟。
seo-title: 即時報表設定
solution: Analytics
title: 即時報表設定
topic: 管理工具
uuid: f48692a0-77c0-4ee4-b3ec-eaa842d06ac8
translation-type: tm+mt
source-git-commit: 45e3330adb562ec795d287ae1c1fa6b03a2b2a31

---


# 即時報表設定

設定即時報表的管理步驟。

在 Reports &amp; Analytics 中設定即時報告，包括選取報表套裝，以及為其選取最多 3 個報告。

1. 選取您要啟用即時報告的報表套裝。

   Navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL View All Reports &gt; Site Metrics]** &gt; **[!UICONTROL Real-Time]** and select the report suite from the drop-down at the top:

   ![](assets/report_suite_selector.png)

   如果您嘗試對尚未設定即時報表的報表套裝檢視即時報表，會出現一則訊息，供您設定報表套裝。

   ![](assets/rep_suite_not_set_up.png)

1. Click **[!UICONTROL Configure]** (gear icon) to run the [!UICONTROL Report Suite Manager].

   (Also available under **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Real-Time]**.)

1. Turn on the **[!UICONTROL Enable Real-Time]** setting.
1. 設定最多 3 個報告的即時資料收集，每個報告各一個量度和三個維度或分類。

   ![](assets/real_time_admin.png)

   如需支援的即時度量和維度的詳細資訊，請參 [閱支援的度量和維度](/help/admin/admin/realtime/realtime-metrics.md)。

   如果您已定義分類，則會以縮排顯示在其所定義的維度下方:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >對於單一即時報表，我們目前不支援啟用重複維度，即使為每個維度選取了不同的分類亦然。

   如需分類的詳細資訊，請參 [閱關於分類](/help/components/c-classifications2/c-classifications.md)。

   >[!NOTE]
   >
   >有些維度（例如「搜尋關鍵字」或「產品」）不會像Adobe Analytics中其他地方一樣，在即時中持續存在。 選取非持續性的量度時，會出現此警告:

   ![](assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   初始設定報告後，最多可能需要 20 分鐘，才會開始串流資料。從那時起，資料就立即可用。如需檢視即時報告的詳細資訊，請參閱[執行即時報告](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html)。

1. 依預設，所有使用者都能存取即時報告。

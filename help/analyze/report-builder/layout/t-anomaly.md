---
description: 關於如何在報告建立工具建立異常偵測請求的步驟。
title: 設定異常偵測請求
topic: Report builder
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 設定異常偵測請求

關於如何在 Report Builder 建立異常偵測請求的步驟。

1. 選取趨勢化報表，如&#x200B;**網站度量**&gt;**[!UICONTROL 流量]**&#x200B;報表。
1. In the [!UICONTROL Apply Granularity] menu, select **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >The [!UICONTROL Anomaly Detection] menu is available only when you select Day granularity. 前 30 天的資料用於統計資料培訓期間，無論您選取的日期範圍為何。

1. After configuring date ranges, click **[!UICONTROL Next]**.

   步驟結果 1。On the Request Wizard: Step 2 of 2, add a metric, such as **[!UICONTROL Visits]**.

   步驟結果 1。For the added metric, click the **[!UICONTROL None]** link.

   ![步驟結果](assets/anomaly_select.png)

1. Select **[!UICONTROL Anomaly Detection]** &gt; **[!UICONTROL `<selection>`]**.

   ![步驟資訊](assets/anomaly_visit.png)

   當您選取其中一選項時，系統會建立原始度量異常偵測的複本。例如，對於造訪次數度量，將新增下界限造訪次數至[!UICONTROL 度量]群組。
1. Click **[!UICONTROL Finish]** and select the cell for output to Excel.

   See [Anomaly Detection](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) for definitions.

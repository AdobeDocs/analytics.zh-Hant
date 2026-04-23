---
description: Details on the Analysis Workspace template, and reporting in Report Builder.
title: 報告 Adobe Analytics 中的 Advertising 資料
feature: Advertising Analytics
exl-id: bbc830d9-e168-471d-a1ba-308277aab415
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 4%

---

# Report on advertising data

本文提供有關Analysis Workspace報表與Report Builder報表的詳細資訊。

>[!NOTE]
>
>搜尋引擎資料會在24小時之後開始填入Analytics報表，請耐心等候。 Analytics reporting does not return data for hourly granularity, because Adobe Advertising data does not support hourly granularity.

## Paid search report {#section_8173F42B2C784F41B9FD82CBB66F9ADF}

This report lets anyone who implements search engine integration get access to search engine data within Analytics. You can access it via **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Acquisition]** > **[!UICONTROL Advertising Analytics: paid search]**

>[!NOTE]
>
>The Paid search report is visible to all customers, even if you have not implemented any Advertising Accounts. If you try to open the Paid search report for a company that is not provisioned, an error message will explain that you have not configured any search engine account. Select **[!UICONTROL Configure Now]**, which takes you to the [Advertising Account Setup](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) screen.

![](assets/aa_aw.png)  ![](assets/aa_aw2.png) ![](assets/aa_aw3.png) ![](assets/aa_aw4.png)  ![](assets/aa_aw5.png) ![](assets/aa_aw6.png)

| Table/Visualization | 說明 |
|--- |--- |
| Advertising Trends | Daily trended overview for AMO Impressions, AMO Clicks, and AMO Cost. |
| 廣告平台 | 2大平台(Google Ads、Microsoft Advertising)的成本環圈圖。 |
| Ad Platform Totals | Freeform table of the top platforms broken down by AMO Impressions, AMO Clicks, AMO Costs, AMO Avg. Position, AMO Avg. 品質分數。 |
| 帳戶 | Stacked area of cost. |
| Account Totals | Freeform table of the top accounts broken down by the associated metrics. |
| 行銷活動 | 行銷活動成本的長條圖。 |
| 行銷活動總計 | 排名最前的行銷活動的自由表格，依相關量度劃分。 |
| 群組  | Tree map of cost. |
| Group Totals | Freeform table of the top advertising groups broken down by the associated metrics. |
| 廣告 | Horizontal bar chart of impressions, clicks, and cost. |
| Ad Totals | 排名最前的廣告的自由格式表格，依相關量度劃分。 |
| 關鍵字 | 所有關鍵字/比對型別組合的曝光數、點按數和成本的散佈圖。 |
| 關鍵字總計 | Freeform table of the top keyword/match type combinations broken down by the associated metrics. |

## Report Builder {#section_8E0371CF81144C33990D909685D1726E}

As soon as you have set up an Advertising Analytics account, the Advertising Analytics report is made available.

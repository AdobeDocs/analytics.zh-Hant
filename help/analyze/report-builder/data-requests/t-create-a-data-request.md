---
description: 建立基本 Report Builder 資料請求的步驟。
title: 建立資料請求
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 建立 Report Builder 資料請求

建立基本資料請求的步驟。

1. In Excel, click **[!UICONTROL Create]**.
1. 在視窗 [!UICONTROL Request Wizard: Step 1] 中，選取報 [表套裝](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。
1. (選用項目) 選取套用至請求的區段。選取一個或多個區段後，它們就會移動到清單頂部。

   Report Builder 使用區段的方式，與 Adobe Analytics 使用區段的方式相同。請參閱 [Analytics 分段指南](https://marketing.adobe.com/resources/help/zh_TW/analytics/segment/)。1.(選用) 選取要用於分配的[發佈清單](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)。
1. 選擇[報表類型](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)。
1. 指定[日期範圍](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)和報表[粒度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)。
1. 按一下 **[!UICONTROL Next]**.
1. 在[「配置 – 請求精靈: 步驟 2」](/help/analyze/report-builder/layout/layout.md)視窗中，指定配置：

   | 元素 | 說明 |
   |---|---|
   | 樞紐配置 | 提供與標準 Excel 表格相似的列、欄及度量格線配置。使用此配置時，您可以在原始請求中新增劃分請求。 |
   | 自訂配置 | Provides most of the functionality of the [!UICONTROL Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. 這項配置提供舊版富有的彈性。 |

1. On the [!UICONTROL Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL Metrics] grid.
1. On the [!UICONTROL Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL Row Labels] grid.

   「步驟 2」提供的[維度](https://marketing.adobe.com/resources/help/zh_TW/reference/dimensions.html)取決於在「步驟 1」選擇的基礎報表，以及報表套裝的組態。The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL Request Wizard: Step 1] window. 在步驟 2 新增多個維度，是在資料請求中建立劃分的方式。

   See [Add Metrics and Dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) for more information.

---
description: 建立基本報告建立工具資料請求的步驟。
title: 建立資料請求
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 建立報告建立工具資料請求

建立基本資料請求的步驟。

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (選用項目) 選取套用至請求的區段。選取一個或多個區段後，它們就會移動到清單頂部。

   Report Builder 使用區段的方式，與 Adobe Analytics 使用區段的方式相同。請參閱 [Analytics 分段指南](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)。1. （選用）選取要 [用於散發](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) 的發佈清單。
1. Select a [report type](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. 指定日 [期範圍](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) 和報 [表詳細程度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. In the [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) window, specify a layout:

   | 元素 | 說明 |
   |---|---|
   | 樞紐配置 | 提供與標準 Excel 表格相似的列、欄及度量格線配置。 使用此配置時，您可以在原始請求中新增分支請求。 |
   | 自訂配置 | 提供「[!UICONTROL 樞紐配置]」的大部分功能，且可讓您選取將格線中的各個項目放置於試算表中的位置。 這項配置提供舊版富有的彈性。 |

1. 在[!UICONTROL 「度量」]索引標籤中，按兩下 (或拖曳) 樹狀檢視中的度量以將其新增至[!UICONTROL 「度量」]格線。
1. 在[!UICONTROL 「維度」]索引標籤中，按兩下 (或拖曳) 維度以將其加入[!UICONTROL 「列標籤」]格線。

   「步驟 2」提供的[維度](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html)取決於在「步驟 1」選擇的基礎報表，以及報表套裝的組態。維度是能關聯、子關聯於您在「[!UICONTROL 請求精靈: 步驟 1]」視窗中選擇的原始報表類型度量或屬於其分類的項目。在步驟 2 新增多個維度是在資料請求中建立分支的方式。

   請參閱[新增度量和維度](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)以取得詳細資訊。

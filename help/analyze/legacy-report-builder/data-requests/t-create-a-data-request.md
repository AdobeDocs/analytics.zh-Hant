---
description: 建立基本 Report Builder 資料請求的步驟。
title: 建立資料請求
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 99%

---

# 建立 Report Builder 資料請求

{{legacy-arb}}

建立基本資料請求的步驟。

1. 在 Excel 中按一下&#x200B;**[!UICONTROL 「建立」]**。
1. 在[!UICONTROL 「請求精靈: 步驟 1」]視窗中選擇[報表套裝](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。
1. (選用項目) 選取套用至請求的區段。選取一個或多個區段後，它們就會移動到清單頂部。

   Report Builder 使用區段的方式，與 Adobe Analytics 使用區段的方式相同。請參閱 [Analytics 分段指南](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)。
1. 選擇[報表類型](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)。
1. 指定[日期範圍](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)和報表[粒度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 在[「配置 – 請求精靈: 步驟 2」](/help/analyze/legacy-report-builder/layout/layout.md)視窗中，指定配置：

   | 元素 | 說明 |
   |---|---|
   | 樞紐配置 | 提供與標準 Excel 表格相似的列、欄及度量格線配置。使用此配置時，您可以在原始請求中新增劃分請求。 |
   | 自訂配置 | 提供「[!UICONTROL 樞紐配置]」的大部分功能，且可讓您選取將格線中的各個項目放置於試算表中的位置。這項配置提供舊版富有的彈性。 |

1. 在[!UICONTROL 「度量」]索引標籤中，按兩下 (或拖曳) 樹狀檢視中的度量以將其新增至[!UICONTROL 「度量」]格線。
1. 在[!UICONTROL 「維度」]索引標籤中，按兩下 (或拖曳) 維度以將其加入[!UICONTROL 「列標籤」]格線。

   「步驟 2」提供的[維度](https://experienceleague.adobe.com/docs/analytics/analyze/legacy-report-builder/layout/filter-dimenson/filter-dimensions.html)取決於在「步驟 1」選擇的基礎報表，以及報表套裝的組態。維度是能關聯、子關聯於您在「[!UICONTROL 請求精靈: 步驟 1]」視窗中選擇的原始報表類型度量或屬於其分類的項目。在步驟 2 新增多個維度，是在資料請求中建立劃分的方式。

   如需詳細資訊，請參閱[新增量度和維度](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)。

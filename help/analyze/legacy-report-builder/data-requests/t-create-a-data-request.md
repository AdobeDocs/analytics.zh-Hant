---
description: 建立基本 Report Builder 資料請求的步驟。
title: 建立資料請求
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
TQID: https://experienceleague.adobe.com/w-oiIfs1qFMoQbaN8YrNIn1TRNHeN97lQOlkLeXdLb0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 77%

---

# 建立 Report Builder 資料請求

{{legacy-arb}}

建立基本資料請求的步驟。

1. 在 Excel 中按一下&#x200B;**[!UICONTROL 「建立」]**。
1. 在[!UICONTROL 「請求精靈: 步驟 1」]視窗中選擇[報表套裝](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)。
1. (選用項目) 選取套用至請求的區段。 選取一個或多個區段後，它們就會移動到清單頂部。

   Report Builder 使用區段的方式，與 Adobe Analytics 使用區段的方式相同。 請參閱 [Analytics 分段指南](/help/components/segmentation/seg-home.md)。
1. 選擇[報表類型](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)。
1. 指定[日期範圍](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)和報表[顆粒度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 在[「配置 – 請求精靈: 步驟 2」](/help/analyze/legacy-report-builder/layout/layout.md)視窗中，指定配置：

   | 元素 | 說明 |
   |---|---|
   | 樞紐配置 | 提供與標準 Excel 表格相似的列、欄及度量格線配置。 使用此配置時，您可以在原始請求中新增劃分請求。 |
   | 自訂配置 | 提供「[!UICONTROL 樞紐配置]」的大部分功能，且可讓您選取將格線中的各個項目放置於試算表中的位置。 此版面配置提供舊版中可用的彈性。 |

1. 在[!UICONTROL 「度量」]索引標籤中，按兩下 (或拖曳) 樹狀檢視中的度量以將其新增至[!UICONTROL 「度量」]格線。
1. 在[!UICONTROL 「維度」]索引標籤中，按兩下 (或拖曳) 維度以將其加入[!UICONTROL 「列標籤」]格線。

   步驟2中可用的[維度](/help/analyze/report-builder/filter-dimensions.md)取決於您在步驟1中選取的基本報表，以及報表套裝的設定。 維度是具有關聯、子關聯的專案，或是您在[!UICONTROL 請求精靈：步驟1]視窗中所選原始報表型別量度的分類。 在步驟 2 新增多個維度，是在資料請求中建立劃分的方式。

   如需詳細資訊，請參閱[新增量度和維度](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)。

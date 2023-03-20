---
description: Analysis Workspace 中的資料字典允許使用者對 Analysis Workspace 中的各種元件建立目錄和追蹤，包括其預定用途、已核准的元件、重複的元件等等。
title: 編輯資料字典中的條目
feature: Components
role: Admin
source-git-commit: 8edd7b1b90e2ac3137bea734e5a0f1cb8004e743
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 63%

---

# 編輯資料字典中的元件條目

{{release-limited-testing}}

Analytics 管理員可以針對特定的報告套裝編輯資料字典中的元件條目。報告套裝的所有使用者都可以看到所做的任何變更。

若要編輯資料字典中的元件條目：

1. 前往包含要編輯之元件的 Analysis Workspace 專案。

1. 選取 Analysis Workspace 左邊欄的&#x200B;**資料字典**&#x200B;圖示。(存取資料字典的替代方法說明請見[資料字典概觀](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)中的「存取資料字典」。)

   顯示資料字典視窗。

   ![資料字典管理員檢視](assets/data-dictionary-admin.png)

1. 確定在下拉選單中選取正確的報告套裝。依預設情況下，會顯示您已使用的報告套裝。

1. (可選) 開始在搜尋欄位中鍵入要編輯的元件名稱。

   元件名稱旁會顯示圖示，指出元件類型：

   | 圖示 | 含義 |
   |---------|----------|
   | ![Dimension圖示](assets/dimension-icon.png) | 表示 **維度**. Dimension由Adobe提供。 無法修改現有維，也無法建立新維。 |
   | ![量度圖示](assets/default-metric-icon.png) | 表示 **標準量度** （未計算）。 標準量度由Adobe提供，無法修改。 |
   | ![Adobe圖示](assets/default-calc-metric-icon.png) | 表示 **計算量度範本**. 這些是由Adobe提供且無法修改的計算量度。 |
   | ![計算器表徵圖](assets/calculated-metric-icon-created.png) | 表示 **計算量度** 由貴組織中的Analytics管理員建立。 <!-- Delete all the comments... Components with this icon can be modified by an Analytics administrator. New calculated metrics can be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![「區段」圖示](assets/segment-icon.png) | 表示 **區段**. 這些可以是由Adobe提供或由貴組織的Analytics管理員建立的區段。<!-- Segments that were created byComponents with this icon can be modified by an Analytics administrator, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md). New calculated metrics can also be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![日期範圍圖示](assets/date-range-icon.png) | 表示 **日期範圍**. 這些可以是Adobe提供的日期範圍，或由貴組織的Analytics管理員建立。 <!-- Components with this icon can be modified by an Analytics administrator. New date ranges can also be created by an Analytics administrator, as described in [Create custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). --> |

{{dd-filter-criteria}}

1. 從元件清單中選取您要編輯的元件。

1. 選擇元件名稱旁邊的&#x200B;**編輯**&#x200B;圖示![資料字典編輯圖示](assets/data-dictionary-edit-icon.png)。

1. 編輯有關元件的以下任何資訊：

   {{dd-component-information}}

1. 按一下&#x200B;**儲存**&#x200B;圖示![資料字典儲存圖示](assets/data-dictionary-save-icon.png)以儲存您的變更。

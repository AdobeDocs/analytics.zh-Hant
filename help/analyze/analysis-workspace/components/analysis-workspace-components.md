---
description: Analysis Workspace 中的元件包含維度、量度、區段及時間範圍；您可將這些元件拖放至專案上。
title: 元件概觀
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: 8856293e4f0114245e32db16809a964ccac5430f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 元件概觀

Analysis Workspace 中的元件包含維度、量度、區段及時間範圍；您可將這些元件拖放至專案上。

若要存取「元件」功能表，請在左側邊欄按一下「**[!UICONTROL 元件]**」圖示。您可以從左側邊欄圖示或使用[熱鍵](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)在[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)、[視覺效果](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)和元件之間切換。

![](assets/component-overview.png)

您也可以調整專案的[檢視密度設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)，以一次在左側邊欄中看到更多值，方法是前往「**[!UICONTROL 專案 > 專案資訊與設定 > 檢視密度]**。

## 維度 {#dimensions}

[**維度**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html)是描述訪客行為的文字屬性，可在您的分析中供檢視、劃分和比較。這些維度可在左側「元件」邊欄 (橘色區段) 中找到，通常可作為表格列套用。

維度的範例包括[!UICONTROL 頁面名稱]、[!UICONTROL 行銷管道]、[!UICONTROL 裝置類型]和[!UICONTROL 產品]。維度是由 Adobe 提供，並透過您的自訂實作 (eVar、Prop、分類等) 擷取。

每個維度也包含&#x200B;**維度項目**&#x200B;在內。維度項目可在左側的「元件」邊欄中找到，只要按一下任何維度名稱旁的右箭頭 (項目為黃色) 即可。

維度項目的範例包括[!UICONTROL 首頁] (在「[!UICONTROL 頁面]」維度內)、[!UICONTROL 付費搜尋] (在「[!UICONTROL 行銷管道]」維度內)、[!UICONTROL Tablet] (在「[!UICONTROL 行動裝置類型]」維度內) 等。

![](assets/dimensions.png)

## 量度 {#metrics}

[**量度**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html)是訪客行為的量化量度。這些量度可在左側「元件」邊欄 (綠色區段) 中找到，通常可作為表格欄套用。

量度的範例包括[!UICONTROL 頁面檢視次數]、[!UICONTROL 瀏覽次數]、[!UICONTROL 訂購]、[!UICONTROL 平均逗留時間]和[!UICONTROL 收入/訂購]。維度是由 Adobe 提供，或是透過您的自訂實作 ([!UICONTROL 成功事件]) 擷取，或是使用[計算量度產生器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)建立。

![](assets/metrics.png)

## 區段 {#segments}

[**區段**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html)是套用至分析的對象篩選器。這些區段可在左側「元件」邊欄 (藍色區段) 中找到，通常套用在面板頂端或表格中量度欄的上方。

區段的範例包括[!UICONTROL 行動裝置訪客人數]、[!UICONTROL 電子郵件的瀏覽次數]和[!UICONTROL 已驗證點擊次數]。區段是由 Adobe 提供，或在[面板下拉區域](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)中建立，或使用[區段產生器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html)建立。

![](assets/segments.png)

## 日期範圍 {#date-ranges}

[**日期範圍**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)是您進行分析的日期範圍。這些日期範圍可在左側「元件」邊欄 (紫色區段) 中找到，通常可套用在每個面板的行事曆中。

可以相對於面板日曆建立日期範圍元件。 有關其他資訊，請參見 [關於相對面板日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)。

日期範圍的範例包括 2019 年 7 月、[!UICONTROL 最近 4 週]和[!UICONTROL 本月]。日期範圍是由 Adobe 提供，或在[面板行事曆](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)中套用，或使用[日期範圍產生器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)建立。

![](assets/date-ranges.png)


## 管理元件 {#actions}

可以直接在左滑軌中管理元件。

1. 按一下右鍵元件。

   或

   選擇元件，然後選擇 **操作** (3-dot)表徵圖。

   >[!TIP]
   >
   >   可通過按住Shift鍵或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上）來選取多個元件。


   ![](assets/component-actions.png)

   | 元件操作 | 說明 |
   |--- |--- |
   | [!UICONTROL **標記**] | 以套用標記的方式組織或管理元件。然後，您可以按一下篩選或輸入 #，依左側欄中的標籤進行搜尋。標籤也會當作元件管理員中的篩選器。 |
   | [!UICONTROL **我的最愛**] | 新增元件至我的最愛清單。如同標籤，您可以依左側邊欄的「我的最愛」搜尋，並在元件管理員中這些條件篩選。 |
   | [!UICONTROL **核准**] | 將元件標示為「已核准」，向您的用戶表示此元件已獲得組織核准。如同標籤，您可以依左側邊欄的「已核准」搜尋，並在元件管理員中這些條件篩選。 |
   | [!UICONTROL **共用**] | 缃元件提供給組織中的用戶共用。此選項僅適用於自訂元件，例如區段或計算量度。 |
   | [!UICONTROL **刪除**] | 刪除您不再需要的元件。 此選項僅適用於自訂元件，例如區段或計算量度。 |

自訂元件也可透過其各自的元件管理員來管理。例如[區段管理員](/help/components/segmentation/segmentation-workflow/seg-manage.md)。

## 搜索、篩選和排序元件清單

您可以搜索、篩選和排序Analysis Workspace左滑軌中的元件清單，以快速找到特定的元件。

### 搜索元件清單

1. 選擇 **元件** 表徵圖 ![元件表徵圖](assets/components-icon.png) 左欄。

1. 在搜索欄位中，開始鍵入要在項目中使用的元件的名稱。

   元件類型可以同時用顏色和表徵圖來標識。 **Dimension** ![Dimension表徵圖](assets/dimension-icon.png) 是橙色的， **段** ![段表徵圖](assets/segment-icon.png) 是藍色的， **日期範圍** ![日期範圍表徵圖](assets/date-range-icon.png) 是紫色的 **度量** ![度量表徵圖](assets/default-metric-icon.png) 是綠色的。 Adobe表徵圖 ![Adobe表徵圖](assets/default-calc-metric-icon.png) 指示計算的度量模板或段模板，以及計算器表徵圖 ![計算器表徵圖](assets/calculated-metric-icon-created.png) 指明了由組織中的分析管理員建立的計算度量。

1. 當元件出現在下拉清單中時，選擇它。

### 篩選元件清單

{{release-limited-testing-section}}

1. 選擇 **元件** 表徵圖 ![元件表徵圖](assets/components-icon.png) 左欄。

1. 選擇 **篩選** 表徵圖 ![「資料字典篩選器」表徵圖](assets/components-filter-icon.png)。

   或

   在搜索欄位中鍵入井號(#)。

1. 選擇以下任何篩選器選項以篩選元件清單：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **已核准**] | 僅顯示標記為由管理員核准的元件。 |
   | [!UICONTROL **我的最愛**] | 僅顯示「我的最愛」清單中的元件。有關將元件新增到「我的最愛」清單的資訊，請參閱[元件概觀](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。 |
   | [!UICONTROL **維度**] | 僅顯示維度的元件。 |
   | [!UICONTROL **量度**] | 僅顯示量度的元件。 |
   | [!UICONTROL **區段**] | 僅顯示區段的元件。<!--this is Filters in CJA--> |
   | [!UICONTROL **日期範圍**] | 僅顯示日期範圍的元件。 |
   | [!UICONTROL **全部顯示**] | 顯示所有元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **未經核准**] | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |

1. （可選）要進一步改進清單，可以按中所述對元件清單進行排序 [對元件清單排序](#sort-the-component-list)。

### 對元件清單排序

1. （可選）將任何篩選器應用到元件清單，如中所述 [篩選元件清單](#filter-the-component-list)。

1. 選擇 **元件** 表徵圖 ![元件表徵圖](assets/components-icon.png) 左欄。

1. 選擇 **排序** 表徵圖 ![「排序元件」表徵圖](assets/component-sort-icon.png)，然後選擇下列任何篩選器選項對元件清單進行排序：

   {{components-sort-options}}

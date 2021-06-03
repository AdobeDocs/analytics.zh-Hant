---
description: 'Analysis Workspace 中的元件包含維度、量度、區段及時間範圍；您可將這些元件拖放至專案上。 '
title: 元件概觀
feature: Workspace 基本知識
role: Business Practitioner, Administrator
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 92%

---

# 元件概觀

Analysis Workspace 中的元件包含維度、量度、區段及時間範圍；您可將這些元件拖放至專案上。

若要存取「元件」功能表，請在左側邊欄按一下「**[!UICONTROL 元件]**」圖示。您可以從左側邊欄圖示或使用[熱鍵](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)在[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant)、[視覺效果](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hant)和元件之間切換。

![](assets/component-overview.png)

您也可以調整專案的[檢視密度設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hant)，以一次在左側邊欄中看到更多值，方法是前往「**[!UICONTROL 專案 > 專案資訊與設定 > 檢視密度]**。

## 維度 {#dimensions}

[**維度**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html)是描述訪客行為的文字屬性，可在您的分析中供檢視、劃分和比較。這些維度可在左側「元件」邊欄 (橘色區段) 中找到，通常可作為表格列套用。

維度的範例包括[!UICONTROL 頁面名稱]、[!UICONTROL 行銷管道]、[!UICONTROL 裝置類型]和[!UICONTROL 產品]。維度是由 Adobe 提供，並透過您的自訂實施作業 (eVar、Prop、分類等) 擷取。

每個維度也包含&#x200B;**維度項目**&#x200B;在內。維度項目可在左側的「元件」邊欄中找到，只要按一下任何維度名稱旁的右箭頭 (項目為黃色) 即可。

維度項目的範例包括[!UICONTROL 首頁] (在「[!UICONTROL 頁面]」維度內)、[!UICONTROL 付費搜尋] (在「[!UICONTROL 行銷管道]」維度內)、[!UICONTROL Tablet] (在「[!UICONTROL 行動裝置類型]」維度內) 等。

![](assets/dimensions.png)

## 量度 {#metrics}

[**量度**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html)是訪客行為的量化度量。這些量度可在左側「元件」邊欄 (綠色區段) 中找到，通常可作為表格欄套用。

度量的範例包括[!UICONTROL 頁面檢視次數]、[!UICONTROL 瀏覽次數]、[!UICONTROL 訂購]、[!UICONTROL 平均逗留時間]和[!UICONTROL 收入/訂購]。維度是由 Adobe 提供，或是透過您的自訂實施作業 ([!UICONTROL 成功事件]) 擷取，或是使用[計算量度產生器](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)建立。

![](assets/metrics.png)

## 區段 {#segments}

[**區段**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)是套用至分析的對象篩選器。這些區段可在左側「元件」邊欄 (藍色區段) 中找到，通常套用在面板頂端或表格中量度欄的上方。

區段的範例包括[!UICONTROL 行動裝置訪客人數]、[!UICONTROL 電子郵件的瀏覽次數]和[!UICONTROL 已驗證點擊次數]。區段是由 Adobe 提供，或在[面板下拉區域](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)中建立，或使用[區段產生器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html)建立。

![](assets/segments.png)

## 日期範圍 {#date-ranges}

[**日期範圍**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)是您進行分析的日期範圍。這些日期範圍可在左側「元件」邊欄 (紫色區段) 中找到，通常可套用在每個面板的行事曆中。

日期範圍的範例包括 2019 年 7 月、[!UICONTROL 最近 4 週]和[!UICONTROL 本月]。日期範圍是由 Adobe 提供，或在[面板行事曆](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)中套用，或使用[日期範圍產生器](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)建立。

![](assets/date-ranges.png)

## 元件動作 {#actions}

您可以直接在左側邊欄中管理元件 (個別或選取多個元件)。在一個元件按一下右鍵，或按一下元件清單頂端的「操作」點圖示。

![](assets/component-actions.png)

| 元件動作 | 說明 |
|--- |--- |
| 標記 | 以套用標記的方式組織或管理元件。然後，您可以按一下篩選或輸入 #，依左側欄中的標籤進行搜尋。標籤也會當作元件管理員中的篩選器。 |
| 我的最愛 | 新增元件至我的最愛清單。如同標籤，您可以依左側邊欄的「我的最愛」搜尋，並在元件管理員中這些條件篩選。 |
| 核准 | 將元件標示為「已核准」，向您的使用者表示此元件已獲得組織核准。如同標籤，您可以依左側邊欄的「已核准」搜尋，並在元件管理員中這些條件篩選。 |
| 共用 | 缃元件提供給組織中的使用者共用。此選項僅適用於自訂元件，例如區段或計算量度。 |
| 刪除 | 刪除您不再需要的元件。 此選項僅適用於自訂元件，例如區段或計算量度。 |

自訂元件也可透過其各自的元件管理員來管理。例如[區段管理員](/help/components/segmentation/segmentation-workflow/seg-manage.md)。

---
description: 'Analysis Workspace地區的元件由維度、量度、區段和日期範圍組成，您可以將這些範圍拖放至專案上。 '
title: 元件概觀
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 17%

---


# 元件概觀

Analysis Workspace地區的元件由維度、量度、區段和日期範圍組成，您可以將這些範圍拖放至專案上。

若要存取「元件」功能表，請按一下左側導軌中的&#x200B;**[!UICONTROL 元件]**&#x200B;圖示。 您可以從左側導軌圖示或使用[熱鍵](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)在[面板](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/panels/panels.html)、[視覺化](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)和元件之間切換。

![](assets/component-overview.png)

您也可以調整專案的[檢視密度設定](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)，以一次在左側導軌中檢視更多值，方法是前往&#x200B;**[!UICONTROL 專案>專案資訊與設定>檢視密度]**。

## 維度 {#dimensions}

[**維度**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) 是描述訪客行為的文字屬性，可在分析中檢視、劃分和比較。它們可在左側的「元件」邊欄（橘色區段）中找到，通常會套用為表格的列。

維度的範例包括[!UICONTROL 頁面名稱]、[!UICONTROL 行銷管道]、[!UICONTROL 裝置類型]和[!UICONTROL 產品]。 Dimension是由Adobe提供，並透過您的自訂實作(eVar、Prop、分類等)擷取。

每個維度也包含&#x200B;**維度項目**。 Dimension項目可按一下任何維度名稱旁的右箭頭（項目為黃色），即可在左側的「元件」邊欄中找到。

維度項目的範例包括：[!UICONTROL Homepage]（在[!UICONTROL Page]維度內）、[!UICONTROL 付費搜尋]（在[!UICONTROL 行銷管道]維度內）、[!UICONTROL Tablet]（在[!UICONTROL 行動裝置類型內）a11/>維度)等。]

![](assets/dimensions.png)

## 量度 {#metrics}

[**量**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) 度是訪客行為的量化度量。它們可在左側的「元件」邊欄（綠色部分）中找到，通常會套用為表格的欄。

度量的範例包括[!UICONTROL 頁面檢視]、[!UICONTROL 瀏覽]、[!UICONTROL 訂購]、[!UICONTROL 平均逗留時間]和[!UICONTROL 收入／訂購]。 量度是由Adobe提供，或是透過您的自訂實作（[!UICONTROL 成功事件]）擷取，或是使用[計算量度產生器](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)建立。

![](assets/metrics.png)

## 區段 {#segments}

[**區**](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) 段是套用至分析的對象篩選。它們可在左側的「元件」邊欄（藍色區段）中找到，通常套用在面板頂端或表格中量度欄上方。

區段的範例包括[!UICONTROL 行動裝置訪客]、[!UICONTROL 電子郵件瀏覽]和[!UICONTROL 已驗證點擊]。 區段是由Adobe提供，或在[面板dropzone](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)中建立，或使用[區段產生器](https://docs.adobe.com/content/help/zh-Hant/analytics/components/segmentation/segmentation-workflow/seg-build.html)建立。

![](assets/segments.png)

## 日期範圍 {#date-ranges}

[**日期**](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) 範圍是您進行分析的日期範圍。它們可在左側的「元件」邊欄（紫色部分）中找到，並通常套用至每個面板的日曆中。

日期範圍的範例包括2019年7月、[!UICONTROL 最近4週]和[!UICONTROL 本月]。 日期範圍由Adobe提供，套用在[面板日曆](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)中，或使用[日期範圍產生器](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)建立。

![](assets/date-ranges.png)

## 元件動作 {#actions}

您可以直接在左側導軌中管理元件（個別或選取多個元件）。 按一下右鍵元件，或按一下元件清單頂部的「操作點」表徵圖。

![](assets/component-actions.png)

| 元件動作 | 說明 |
|--- |--- |
| 標記 | 以套用標記的方式組織或管理元件。然後，您可以按一下篩選或輸入#，依左側欄中的標籤進行搜尋。 標籤也會當成元件管理員中的篩選器。 |
| 我的最愛 | 新增元件至我的最愛清單。如同標籤，您可以依左側邊欄的「我的最愛」搜尋，並在元件管理員中依其篩選。 |
| 核准 | 將元件標示為「已核准」，以向您的使用者指出元件已組織核准。 如同標籤，您可以在左側邊欄中依「已核准」搜尋，並在元件管理員中依其篩選。 |
| 共用 | 將元件共用給組織中的使用者。 此選項僅適用於自訂元件，例如區段或計算量度。 |
| 刪除 | 刪除您不再需要的元件。 此選項僅適用於自訂元件，例如區段或計算量度。 |

自訂元件也可透過其各自的元件管理員來管理。 例如，[區段管理員](/help/components/segmentation/segmentation-workflow/seg-manage.md)。

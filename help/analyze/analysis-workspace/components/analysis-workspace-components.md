---
description: '分析工作區中的元件由維度、量度、區段和日期範圍組成，您可以將這些範圍拖放至專案上。 '
title: 元件概述
translation-type: tm+mt
source-git-commit: 459d650b30355912f4c9195c05da6728610109e8
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 13%

---


# 元件概述

分析工作區中的元件由維度、量度、區段和日期範圍組成，您可以將這些範圍拖放至專案上。

To access the Components menu, click the **[!UICONTROL Components]** icon in the left rail. 您可從左側導 [軌圖示或使](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)用熱鍵，在「面板 [」、「視覺化」和「元件」](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)之間切換 [](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。

![](assets/component-overview.png)

您也可以調整專案 [的「檢視密度」設定](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) ，以便一次在左側導軌中檢視更多值，方法是前往「 **[!UICONTROL 專案>專案資訊與設定>檢視密度」]**。

## 維度 {#dimensions}

[**維度**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) 是描述訪客行為的文字屬性，可在分析中檢視、劃分和比較。 它們可在左側的「元件」邊欄（橘色區段）中找到，通常會套用為表格的列。

維度的範例包 [!UICONTROL 括頁面名稱]、 [!UICONTROL 行銷管道]、 [!UICONTROL 裝置類型], 以及產品。 維度由Adobe提供，並透過您的自訂實作（eVar、Prop、分類等）擷取。

每個維度也包含 **其中的維度** 項目。 按一下任何維度名稱旁的向右箭頭（項目為黃色），即可在左側的「元件」邊欄中找到維度項目。

維度項目的範例包括 [!UICONTROL 首頁] (在 [!UICONTROL Homepage] )、 [!UICONTROL Paid Search(在] Marketing Channel Dimension中)、ChatLight（在Tablet Device Dimension中）、Chight（在Trablet Mobile Dimension）等等等。

![](assets/dimensions.png)

## 量度 {#metrics}

[**量度**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) 是訪客行為的量化度量。 它們可在左側的「元件」邊欄（綠色部分）中找到，通常會套用為表格的欄。

度量的範例包括 [!UICONTROL 頁面檢視]、 [!UICONTROL 瀏覽]、 [!UICONTROL 訂購]、平均 逗留時間、訂購／訂購收入。 量度由Adobe提供，或透過您的自訂實作([!UICONTROL 成功事件])擷取，或使用計算量度產 [生器建立](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)。

![](assets/metrics.png)

## 區段 {#segments}

[**區段**](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) 是套用至分析的對象篩選。 它們可在左側的「元件」邊欄（藍色區段）中找到，通常套用在面板頂端或表格中量度欄上方。

區段的範例包括 [!UICONTROL 行動裝置訪客]、 [!UICONTROL 來自電子郵件的瀏]覽 [!UICONTROL ，以及]已驗證點擊。 區段是由Adobe提供、在面板下拉區中建 [立](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)，或使用區段產生 [器建立](https://docs.adobe.com/content/help/zh-Hant/analytics/components/segmentation/segmentation-workflow/seg-build.html)。

![](assets/segments.png)

## 日期範圍 {#date-ranges}

[**日期範圍**](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) ，是您進行分析的日期範圍。 它們可在左側的「元件」邊欄（紫色部分）中找到，並通常套用至每個面板的日曆中。

日期範圍的範例包括2019年7月、 [!UICONTROL 最近4週]、 [!UICONTROL 本月]。 日期範圍由Adobe提供、套用至面板行事 [歷](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)，或使用日期範圍產 [生器建立](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)。

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

自訂元件也可透過其各自的元件管理員來管理。 例如，區段 [管理員](/help/components/segmentation/segmentation-workflow/seg-manage.md)。

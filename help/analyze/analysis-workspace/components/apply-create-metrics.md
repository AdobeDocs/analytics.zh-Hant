---
description: 在 Analysis Workspace 中使用量度有兩種方式。
title: Analysis Workspace 中的量度
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: c1b679dab7b66754ae4b6fd7503243f40d0f2178
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 24%

---

# 量度

量度可讓您量化Analysis Workspace中的資料點。 它們最常用作視覺效果中的欄，並與維度繫結。

## 量度型別

Adobe提供數種用於Analysis Workspace的量度型別：

* **標準量度**：您在專案中使用的大部分量度都是標準量度。 範例包括 [頁面檢視](/help/components/metrics/page-views.md)， [收入](/help/components/metrics/revenue.md)，或 [自訂事件](/help/components/metrics/custom-events.md). 另請參閱 [量度概觀](/help/components/metrics/overview.md) 詳細資訊，請參閱「元件」使用指南。

   ![標準量度](assets/standard-metric.png)

* **計算量度**：根據標準量度、靜態數字或演演算法函式的使用者定義量度。 使用者定義的計算量度會在可用元件清單中顯示計算器圖示。 另請參閱 [計算量度概觀](/help/components/c-calcmetrics/cm-overview.md) 詳細資訊，請參閱「元件」使用指南。

   ![計算量度](assets/calculated-metric.png)

* **計算量度範本**：Adobe定義的量度，其行為與計算量度類似。 您可以在Workspace專案中照原樣使用它們，或儲存副本以自訂其邏輯。 計算量度範本會在可用元件清單中顯示Adobe圖示。

   ![計算量度範本](assets/calculated-metric-template.png)

## 在Analysis Workspace中使用量度

量度可在Analysis Workspace中以各種方式使用。 您可以：

* 將量度拖曳至空白的自由格式表格，以檢視專案日期期間的量度趨勢。

* 出現維度時拖曳量度，以檢視該量度與每個維度專案的比較。

* 將量度拖曳至現有量度標題上方，藉此取代。

* 拖曳標頭旁的量度，讓兩個量度並排顯示。

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## 計算量度

計算量度可讓您使用簡單的運運算元或統計函式，輕鬆檢視量度彼此之間的關係。 建立計算量度有數種方式：

* 按一下左側元件清單下「量度」標題旁的加號圖示。
* 導覽至 **[!UICONTROL 元件]** > **[!UICONTROL 計算量度]** > **[!UICONTROL 新增]**.
* 以滑鼠右鍵按一下欄標題> **[!UICONTROL 從選取範圍建立量度]** 選取一或多個標頭欄儲存格時。 此選項會自動為您建立計算量度，而不需要使用計算量度規則產生器。

[計算量度：實作較少的量度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=zh-Hant) (3:42)

## 比較不同歸因模型的量度

如果您想要快速輕鬆地比較一個歸因模型與另一個歸因模型，請在量度按一下右鍵，然後選取「**[!UICONTROL 比較歸因模型]**」：

![比較歸因](assets/compare-attribution.png)

此快速鍵可讓您輕鬆快速地比較不同的歸因模型，而無須再次拖曳量度和進行設定。

## 使用[!UICONTROL 累積平均]函數以套用量度平滑處理

以下是有關該主題的影片：

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)

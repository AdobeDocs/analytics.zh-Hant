---
description: 在 Analysis Workspace 中使用量度有兩種方式。
title: Analysis Workspace 中的量度
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: 56fd6dd8450df3ffea78154fafa1e858d5a653a7
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 23%

---

# 量度

指標允許您量化Analysis Workspace的資料點。 它們通常用作可視化中的列，並與尺寸關聯。

Adobe提供了幾種在Analysis Workspace使用的指標：

* **標準度量**:在項目中使用的大多數指標都是標準指標。 示例包括 [頁面視圖](/help/components/metrics/page-views.md)。 [收入](/help/components/metrics/revenue.md)或 [自定義事件](/help/components/metrics/custom-events.md)。 請參閱 [度量概述](/help/components/metrics/overview.md) 的子菜單。

   ![標準度量](assets/standard-metric.png)

* **計算的度量**:基於標準度量、靜態數或算法函式的用戶定義的度量。 用戶定義的計算度量在可用元件清單中顯示計算器表徵圖。 請參閱 [計算度量概覽](/help/components/c-calcmetrics/cm-overview.md) 的子菜單。

   ![計算度量](assets/calculated-metric.png)

* **計算的度量模板**:Adobe定義的度量，其行為與計算度量類似。 您可以在Workspace項目中按原樣使用它們，或保存副本以自定義其邏輯。 計算的度量模板在可用元件清單中顯示Adobe表徵圖。

   ![計算的度量模板](assets/calculated-metric-template.png)

指標在Analysis Workspace的使用是靈活的。 將度量拖到空的自由形式表中，以查看該度量在項目的日期期間內的趨勢。 當存在維時，還可以拖動度量以查看與每個維項相比的度量。 在現有度量標頭上拖動度量將替換它，並在標頭旁拖動度量可同時查看兩個度量。

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## 計算量度

通過計算度量，您可以使用簡單的運算子或統計函式輕鬆地查看度量之間的關聯。 有幾種方法可建立計算度量：

* 按一下左側元件清單下「度量」標題旁的加號表徵圖。
* 導航到 **[!UICONTROL 元件]** > **[!UICONTROL 計算度量]** > **[!UICONTROL 添加]**。
* 按一下右鍵列標題> **[!UICONTROL 從選擇建立度量]** 選擇一個或多個標題列單元格時。 此選項可自動為您建立計算度量，而無需使用計算度量規則生成器。

[計算量度：實作較少的量度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=zh-Hant) (3:42)

## 比較不同歸因模型的量度

如果您想要快速輕鬆地比較一個歸因模型與另一個歸因模型，請在量度按一下右鍵，然後選取「**[!UICONTROL 比較歸因模型]**」：

![比較歸因](assets/compare-attribution.png)

此快速鍵可讓您輕鬆快速地比較不同的歸因模型，而無須再次拖曳量度和進行設定。

## 使用[!UICONTROL 累積平均]函數以套用量度平滑處理

以下是有關該主題的影片：

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)

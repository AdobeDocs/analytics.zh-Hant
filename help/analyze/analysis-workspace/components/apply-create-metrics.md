---
description: 在 Analysis Workspace 中使用量度有兩種方式。
title: Analysis Workspace 中的量度
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 50%

---

# 量度

量度可讓您量化 Analysis Workspace 中的資料點。它們最常用作視覺效果中的欄，並和維度相連結。

## 量度類型

Adobe 提供了多種可用於 Analysis Workspace 中的量度類型：

* **標準量度**：您在專案中使用的大多數量度都屬於標準量度。範例包括[頁面檢視次數](/help/components/metrics/page-views.md)、[營收](/help/components/metrics/revenue.md)或[自訂事件](/help/components/metrics/custom-events.md)。如需詳細資訊，請參閱「元件」使用手冊中的[量度概觀](/help/components/metrics/overview.md)。

  ![標準量度](assets/standard-metric.png)

* **計算量度**：以標準量度、靜態數字或演算法函式為根據的使用者定義量度。使用者定義的計算量度會在可用元件清單中顯示計算機圖示。如需詳細資訊，請參閱「元件」使用手冊中的[計算量度概觀](/help/components/c-calcmetrics/cm-overview.md)。

  ![計算量度](assets/calculated-metric.png)

* **計算量度範本**：Adobe 定義的量度，其行為會類似計算量度。您可以在 Workspace 專案中按原樣使用它們，或另存為副本以自訂其邏輯。計算量度範本會在可用元件清單中顯示 Adobe 圖示。

  ![計算量度範本](assets/calculated-metric-template.png)

## 使用 Analysis Workspace 中的量度

在 Analysis Workspace 中能以多種方式使用量度。如需有關如何將量度和其他型別的元件新增到Analysis Workspace的資訊，請參閱[在Analysis Workspace中使用元件](/help/analyze/analysis-workspace/components/use-components-in-workspace.md)。


>[!BEGINSHADEBOX]

請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [使用量度](https://video.tv.adobe.com/v/40817?quality=12&learn=on){target="_blank"}進行示範影片。

>[!ENDSHADEBOX]



## 建立計算量度

計算量度可讓您使用簡單的運運算元或統計函式，輕鬆檢視量度彼此間的關聯性。

建立計算量度有數種方式。 您選擇的方法會決定計算量度是否可從所有專案的元件清單中使用，或僅用於建立該量度的專案。

### 為所有專案建立計算量度

您可以使用計算量度產生器建立計算量度。 以這種方式建立時，計算量度會顯示在元件清單中，然後可用於整個組織的專案。

如需如何存取計算量度產生器的詳細資訊，請參閱[建立量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)。

### 為單一專案建立計算量度

您可以建立快速計算量度，這些量度只適用於建立所在的專案。

若要建立單一專案的計算量度：

1. 在Analysis Workspace中，開啟您要建立計算量度的專案。

1. 在自由表格中，以滑鼠右鍵按一下一或多個標題欄儲存格，然後選取&#x200B;**[!UICONTROL 從選取範圍建立量度]**

   ![Workspace面板反白顯示「從選取專案建立」](assets/create-metric-from-selection.png)

1. 若要僅為此專案建立計算量度，請從下列選項中選擇：

   * [!UICONTROL **除**]

   * [!UICONTROL **減去**]

   * [!UICONTROL **新增**]

   * [!UICONTROL **乘**]

   或者，若要開啟計算量度產生器並為所有專案建立計算量度，請選取「在計算量度產生器中開啟」[!UICONTROL ****]，然後繼續執行[建立量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)。

[計算量度：實作較少的量度](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=zh-Hant) (3:42)

## 比較不同歸因模型的量度

如果您想要快速輕鬆地比較一個歸因模型與另一個歸因模型，請在量度按一下右鍵，然後選取「**[!UICONTROL 比較歸因模型]**」：

![比較歸因](assets/compare-attribution.png)

此快速鍵可讓您輕鬆快速地比較不同的歸因模型，而無須再次拖曳量度和進行設定。

## 使用[!UICONTROL 累積平均]函數以套用量度平滑處理

以下是有關該主題的影片：


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [累積平均值](https://video.tv.adobe.com/v/27068?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


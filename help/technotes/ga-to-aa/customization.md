---
title: Adobe Analytics中的報表自訂
description: 瞭解如何在Adobe Analytics中自訂報告
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# 自訂報告

在協力廠商平台(例如Google Analytics)中，有一些自訂選項可供使用。這些自訂可讓使用者建立控制面板、自訂報表、儲存的報表和自訂警報。因為Analysis Workspace可讓使用者從空白畫布建立報表，因此大部分自訂都直接內建在工具中。

此頁面假設使用者具備使用分析工作區的基本知識。See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 控制面板

分析工作區的架構建立類似控制面板Widget的概念。「分析工作區」中的專案相當於Google Analytics中的控制面板。「分析工作區」中的視覺效果是Google Analytics中的近似小工具。

### 新增內容至專案

1. 按一下左側的「視覺效果」圖示，並拖曳所要的視覺效果至工作區。
2. 按一下左側的「元件」圖示，拖曳所需維度和度量至視覺化，以填入資料。
3. 拖曳視覺化邊緣以調整其大小，並拖曳視覺化標題以移動它。

Analytics工作區中提供所有Google Analytics Widget：

* **量度介面工具集** 大約等於摘要數字視覺化。
* **時間軸Widget** 大約等於線條視覺效果。
* **地域工具集** 大約等於地圖視覺化。
* **表格介面工具集** 大約等於自由表格視覺化。
* **圓形工具集** 大約等於環圈視覺效果。
* **Bar Widget** 大約等於Bar視覺化。

分析工作區包含許多視覺化選項，以最符合您的報表需求的方式呈現資料。See [Visualizations in Analysis Workspace](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### 共用專案

當您將內容新增至專案後，您可以共用它。

* 若要與同事共用專案，請前往「共用&gt;共用專案」。收件者是您組織中擁有Adobe Analytics帳戶的其他使用者。
* 若要透過連結共用專案，請前往「共用&gt;取得專案連結」。請注意，這仍需要您組織內的Adobe Analytics登入。

### 匯出專案

除了PDF以外，Analysis Workspace還提供CSV匯出。

1. Click *[!UICONTROL Share]* &gt; *[!UICONTROL Send File Now]*, which opens a modal window.
2. 指定檔案類型和收件者。
3. Click [!UICONTROL Send Now].

## 自訂報表

在Google Analytics中建立自訂報表時，需要的欄位類似於在工作區中建立視覺化的工作流程。平台之間的維度、量度和篩選定義類似。在分析工作區中，不會從清單中選取維度和度量，而是拖曳維度和度量至自由表格上。

### 自訂報表中的計算量度

自訂報表是Google Analytics中允許使用計算量度的少數區域之一。由於Analysis Workspace如同畫布般運作，因此計算量度可追溯及在任何上下文中運作。

要建立計算量度:

1. Click the **+** icon near the metric list to open the Calculated Metric Builder.
2. 為您的計算量度指定名稱並指定格式。
3. 拖曳量度元件至定義區域，然後使用每個元件之間的dps指定運算元。
4. 計算量度包含所需的公式後，按一下「儲存」返回您的工作區。
5. 將新定義的計算量度拖曳至工作區上。

   Learn more about [Calculated Metrics](../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

## 自訂警報

警報可在兩個平台上使用。In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* &gt; *[!UICONTROL Alerts]*. See [Intelligent Alerts](../../components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.

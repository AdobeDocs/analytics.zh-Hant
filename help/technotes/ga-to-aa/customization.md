---
title: Adobe Analytics 中的報表自訂功能
description: 瞭解如何在 Adobe Analytics 中自訂報表
translation-type: ht
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# 自訂報表

在 Google Analytics 等協力廠商平台中，有數個自訂選項可供使用。這些自訂功能可讓使用者建立控制面板、自訂報表、已儲存報表，以及自訂警報。由於 Analysis Workspace 可讓使用者從空白畫布建立報表，因此大部分的自訂功能都直接內建在工具中。

本頁假設使用者具備使用 Analysis Workspace 的基本知識。如果您尚不熟悉 Adobe Analytics 中的工具，請參閱[在 Analysis Workspace 中建立基本報表 (Google Analytics 使用者適用)](reports/create-report.md)。

## 控制面板

Analysis Workspace 的架構與控制面板 Widget 的概念類似。Analysis Workspace 中的專案約略等同於 Google Analytics 中的控制面板。Analysis Workspace 中的視覺效果約略等同於 Google Analytics 中的 Widget。

### 新增內容到專案

1. 按一下左側的「視覺效果」圖示，然後將所需的視覺效果拖曳至工作區。
2. 按一下左側的「元件」圖示，然後將所需的維度和量度拖曳至視覺效果，以填入資料。
3. 拖曳視覺效果的邊緣以調整其大小，而拖曳視覺效果的標頭即可移動。

所有 Google Analytics Widget 都可在 Analysis Workspace 中使用：

* **量度 Widget** 約略等同於「摘要數字」視覺效果。
* **時間軸 Widget** 約略等同於「線條圖」視覺效果。
* **Geomap Widget** 約略等同於「地圖」視覺效果。
* **表格 Widget** 約略等同於「自由表格」視覺效果。
* **圓形圖 Widget** 約略等同於「環圈圖」視覺效果。
* **長條圖 Widget** 約略等同於「長條圖」視覺效果。

Analysis Workspace 包含更多視覺效果選項，讓您以最符合報表需求的方式呈現資料。如需詳細資訊，請參閱分析使用指南中的 [Analysis Workspace 中的視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。

### 共用專案

一旦您將內容新增至專案之後，即可加以共用。

* 若要與同事共用專案，請前往「共用 > 共用專案」。收件者是貴組織中擁有 Adobe Analytics 帳戶的其他使用者。
* 若要透過連結共用您的專案，請前往「共用 > 取得專案連結」。請注意，這仍需要在貴組織內登入 Adobe Analytics。

### 匯出專案

除了 PDF 之外，Analysis Workspace 還提供 CSV 匯出功能。

1. 按一下&#x200B;*[!UICONTROL 共用]* > *[!UICONTROL 立即傳送檔案]*&#x200B;以開啟模組視窗。
2. 指定檔案類型和收件者。
3. 按一下[!UICONTROL 立即傳送]。

## 自訂報表

在 Google Analytics 中建立自訂報表時，必填欄位類似在工作區中建立視覺效果時的工作流程。不同平台之間的維度、量度和篩選器定義都類似。在 Analysis Workspace 中，需要將維度和量度拖曳至自由表格，而不是從清單中選取維度和量度。

### 自訂報表中的計算量度

自訂報表是 Google Analytics 中允許使用計算量度的少數區域之一。由於 Analysis Workspace 的運作方式有如畫布，因此計算量度能以回溯的方式運作，而且可在任何情境中運作。

要建立計算量度：

1. 按一下量度清單旁邊的 **+** 圖示開啟「計算量度產生器」。
2. 為您的計算量度命名並指定格式。
3. 將量度元件拖曳至定義區域，然後使用每個元件之間的下拉式清單來指定運算子。
4. 一旦計算量度包含所需公式之後，按一下「儲存」返回您的工作區。
5. 將新定義的計算量度拖曳至工作區。

   進一步瞭解「元件」使用指南中的[計算量度](/help/components/c-variables/c-metrics/calculated-metric.md)。

## 自訂警報

警報可在兩種平台上使用。在 Adobe Analytics 中，使用頁首導覽功能表並前往&#x200B;*[!UICONTROL 元件]* > *[!UICONTROL 警報]*。如需詳細資訊，請參閱元件使用指南中的[智慧型警報](/help/components/c-alerts/intellligent-alerts.md)。

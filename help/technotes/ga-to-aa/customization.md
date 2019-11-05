---
title: Adobe Analytics中的報表自訂
description: 瞭解如何在Adobe Analytics中自訂報表
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# 自訂報表

在Google Analytics等協力廠商平台中，有數個自訂選項可供使用。 這些自訂可讓使用者建立控制面板、自訂報表、儲存的報表和自訂警報。 由於分析工作區可讓使用者從空白畫布建立報表，因此大部分的自訂都直接內建在工具中。

本頁假設使用者具備使用分析工作區的基本知識。 如 [果您尚不熟悉Adobe Analytics中的工具](reports/create-report.md) ，請參閱「Google Analytics使用者分析工作區」中的建立基本報表。

## 控制面板

分析工作區的架構與儀表板Widget的概念類似。 「分析工作區」中的專案大致相當於Google Analytics中的控制面板。 「分析工作區」中的視覺化大致等同於Google Analytics中的Widget。

### 新增內容至專案

1. 按一下左側的「視覺化」圖示，然後將所要的視覺化拖曳至工作區。
2. 按一下左側的「元件」圖示，將所需的維度和量度拖曳至視覺化，以填入資料。
3. 拖曳視覺化的邊緣以調整其大小，並拖曳視覺化的標題以移動它。

所有Google Analytics Widget都可在分析工作區中使用：

* 量度 **介面工具集** ，大致等於「摘要數字」視覺化。
* 時間 **軸介面工具集** ，大致等於線條視覺化。
* Geomap **介面工具集** ，大致等於「地圖」視覺化。
* 表格 **介面工具集** ，大致等於自由表格視覺化。
* 圓形 **圖介面工具集** (Pie widget)與環圈圖視覺化(Donut visualization)大致相同。
* 列 **介面工具集** ，大約等於列視覺化。

分析工作區包含更多視覺化選項，以最符合您報表需求的方式呈現資料。 如需詳 [細資訊，請參閱分析使用指南](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) 「分析工作區中的視覺化」。

### 共用專案

在您將內容新增至專案後，就可以共用它。

* 若要與同事共用專案，請前往「共用&gt;共用專案」。 收件者是您組織中擁有Adobe Analytics帳戶的其他使用者。
* 若要透過連結分享您的專案，請前往「分享&gt;取得專案連結」。 請注意，這仍需要您組織內的Adobe Analytics登入。

### 匯出專案

除了PDF之外，「分析工作區」還提供CSV匯出功能。

1. 按一 *[!UICONTROL 下「共用]* &gt;立 *[!UICONTROL 即傳送檔案]*」，開啟模式視窗。
2. 指定檔案類型和收件者。
3. Click [!UICONTROL Send Now].

## 自訂報表

在Google Analytics中建立自訂報表時，所需欄位類似於在工作區中建立視覺化時的工作流程。 維度、度量和篩選定義在不同平台之間相似。 在分析工作區中，維度和度量會拖曳至自由表格，而不是從清單中選取維度和度量。

### 自訂報表中的計算量度

自訂報表是Google Analytics中允許使用計算量度的少數區域之一。 由於「分析工作區」的運作方式與畫布相同，因此計算量度可追溯運作，而且可在任何情境中運作。

要建立計算量度:

1. 按一下 **量度清單旁的** +圖示，以開啟計算量度產生器。
2. 為您的計算量度指定名稱並指定格式。
3. 將量度元件拖曳至定義區域，然後使用每個元件之間的下拉式清單來指定運算元。
4. 計算量度包含所需公式後，按一下「儲存」返回您的工作區。
5. 將新定義的計算量度拖曳至工作區。

   進一步瞭解「 [元件」使用指南](/help/components/c-variables/c-metrics/calculated-metric.md) 中的「計算量度」。

## 自訂警報

警報可在兩種平台上使用。 在Adobe Analytics中，使用頁首導覽功能表並前往「元件 *[!UICONTROL &gt;警]* 報」 **。 如需詳 [細資訊，請參閱元件](/help/components/c-alerts/intellligent-alerts.md) 使用指南中的智慧型警報。

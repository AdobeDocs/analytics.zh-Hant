---
description: 面板是表格和視覺化的集合
title: 面板概述
translation-type: tm+mt
source-git-commit: c9ceebef6afc60551304ed703050757269d8cb30
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 11%

---


# 面板概述

A [!UICONTROL panel] is a collection of tables and visualizations. 您可以從工作區的左上角圖示或空白麵板中存取 [面板](blank-panel.md)。 當您想要根據時段、報表套裝或分析使用案例來組織專案時，面板會很有幫助。 「分析工作區」中提供下列面板類型：

| 面板名稱 | 說明 |
| --- | --- |
| [空白面板](blank-panel.md) | 從可用的面板和視覺化中選擇，以開始分析。 |
| [快速深入分析面板](quickinsight.md) | 快速建立自由格式表格和隨附的視覺效果，以更快速分析及揭秘深入分析。 |
| [Analytics for Target 面板](a4t-panel.md) | 在 Analysis Workspace 中分析 Target 的活動和體驗。 |
| [歸因面板](attribution.md) | 使用任何維度和轉換度量，快速比較和視覺化任何數量的歸因模型。 |
| [自由表格面板](freeform-panel.md) | 執行不限次數的比較和劃分，然後新增視覺化來呈現豐富的資料故事。 |
| [媒體並行檢視器面板](media-concurrent-viewers.md) | 分析不同時段的同時檢閱者，並取得尖峰檢閱情形的詳細資訊，並可加以劃分及比較。 |
| [區段比較面板](c-segment-comparison/segment-comparison.md) | 快速比較所有資料點的兩個區段，以自動找出相關差異。 |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights]、 [!UICONTROL Blank] 和 [!UICONTROL Freeform] Arytics是您開始分析的絕佳場所，而  Analytics for Analytics、Iq IQ Attribution、Viewers和Target Comparison Cleaming Panels則可讓您同時進行更高級分析。 專案中也有 `"+"` 按鈕可供使用，讓您隨時都可以新增空白面板。

The default starting panel is the [!UICONTROL Freeform] panel, but you can make the [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) your default as well.

## 報表套裝 {#report-suite}

面板中的表格和視覺化會從面板右 [!UICONTROL 上方] ，選取的報表套裝衍生資料。 報表套裝也會決定左側導軌中可用的元件。 在專案中，您可以根據分析使 [用案例使用一](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) 或多個報表套裝。 若要將單一報表套裝套用至專案中的所有面板，請以滑鼠右鍵按 **一下面板標題>將報表套裝套用至所有面板**。

報表套裝清單會依相關性排序，Adobe會根據目前使用者最近和經常使用套裝的情形，以及組織內使用套裝的情形，來定義相關性。

![](assets/panel-report-suite.png)

## 日曆 {#calendar}

面板日曆控制面板中表格和視覺化的報告範圍。

注意：如果在表格、視覺化或面板Dropzone中使用（紫色）日期範圍元件，則會覆寫面板日曆。

![](assets/panel-calendar.png)

## Dropzone {#dropzone}

面板下拉區可讓您將區段和下拉式篩選套用至面板內的所有表格和視覺化。 您可以套用一或多個篩選器至面板。 您可以按一下編輯鉛筆來修改每個濾鏡上方的標題，或以滑鼠右鍵按一下以完全移除。

### 群體篩選

從左側導軌拖放任何區段至面板拖放區域，開始篩選面板。

![](assets/segment-filter.png)

### 臨機群體篩選

您也可以將非區段元件直接拖曳至Dropzone以建立臨機區段，為您省下前往區段產生器的時間和心力。 以此方式建立的區段會自動定義為點擊層級區段。 此定義可修改，方法是按一下區段旁的資訊圖示(i)，然後是鉛筆形編輯圖示，並在區段產生器中加以編輯。

臨機區段是專案的本機區段，除非您將其公開，否則不會顯示在左側導軌中。

![](assets/adhoc-segment-filter.png)

### 下拉式篩選 {#dropdown-filter}

除了區段篩選外，下拉式篩選還可讓您以控制方式與資料互動。 例如，您可以新增「行動裝置類型」的下拉式篩選，以便依平板電腦、行動電話或案頭來劃分面板。

下拉式篩選器也可用來將許多專案合併為一個專案。 例如，如果您有許多版本的相同專案已套用不同的國家／地區區段，則可以將所有版本合併為單一專案，並新增國家／地區下拉式篩選。

![](assets/dropdown-filter-intro.png)

若要建立下拉式篩選：

1. 若要使用維度項目(例如 [!UICONTROL Marketing Channel]dimension中的值)建立下拉式篩選  ，請按一下左側導軌中維度旁的向右箭頭圖示。 這會公開所有可用項目。 從左側導軌中選取一或多個元件項目，並在按住Shift鍵的同 **時將其拖放至面板拖放區**。 這會將元件轉換為下拉式篩選，而非單一區段。
1. 若要使用其他元件（例如量度、區段或日期範圍）建立下拉式篩選，請從左側導軌中的一個元件類型中選取，然後在按住Shift鍵的同 **時拖曳至面板下拉區**。
1. 從下拉式清單中選取其中一個選項，以變更面板中的資料。 You can also choose to not filter any of the panel data by selecting **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

[觀看影片](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) ，進一步瞭解如何將下拉式篩選器新增至專案。

## 右鍵功能表 {#right-click}

以滑鼠右鍵按一下面板標題，即可使用面板的其他功能。 可使用下列設定：

| 設定 | 說明 |
| --- | --- |
| 插入複製的面板／視覺化 | 可讓您將複製的面板或視覺化貼到（「插入」）專案內的其他位置，或貼到完全不同的專案中。 |
| 複製面板 | 可讓您按一下滑鼠右鍵並複製面板，以便將面板插入專案內的其他位置，或插入完全不同的專案。 |
| 套用報表套裝至所有面板 | 可讓您將作用中的面板報表套裝套用至專案中的所有面板。 |
| 複製面板 | 請精確複製目前的面板，然後您可加以修改。 |
| 收合／展開所有面板 | 折疊並展開所有專案面板。 |
| 收合／展開面板中的所有視覺化 | 折疊和展開目前面板中的視覺化。 |
| 編輯描述 | 新增（或編輯）面板的文字說明。 |
| 取得面板連結 | 讓您可將使用者直接導向專案中的特定面板。點按連結時，收件者必須先登入，才能被導向到連結的確切面板。 |

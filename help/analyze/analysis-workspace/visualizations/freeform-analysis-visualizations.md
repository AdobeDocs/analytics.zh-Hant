---
description: 以視覺化方式呈現您的資料。
keywords: Analysis Workspace
title: 視覺效果概述
translation-type: tm+mt
source-git-commit: 71cf46157917c77a815b8474bc635c01d6d13a25
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 42%

---


# 視覺效果概述

工作區提供許多視覺效果，可產生資料的視覺化表示法，例如長條圖、環圈圖、直方圖、折線圖、地圖、散點圖等。如果您使用Adobe Analytics，大部分的視覺化類型都會讓您熟悉。 不過，Analysis Workspace 還提供視覺效果設定，以及許多具有互動功能的新或獨特的視覺效果類型。

您可以從工作區的左上角圖示、空白麵板 [中](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html)，或透過工作流程中的按滑鼠右鍵選單來存取視覺化。 分析工作區中提供下列視覺化類型：

| 視覺效果名稱 | 說明 |
| --- | --- |
| [區域](/help/analyze/analysis-workspace/visualizations/area.md) | 就像線條圖，但線下有彩色區域。 有多個量度且以要視覺化方式表示多個量度之間交會的區域時，可使用區域圖。 |
| [長條圖](/help/analyze/analysis-workspace/visualizations/bar.md) | 顯示代表一或多個量度多個值的垂直長條。 |
| [項目圖表](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | 顯示您感興趣的值與其他效能範圍 (目標) 相比較或進行測量的結果。 |
| [同類群組表格](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | *`cohort`* 是指一段指定時間內，共享相同特徵的一組人。世代分析對保留、流失或延遲分析非常有用。 |
| [環形圖](/help/analyze/analysis-workspace/visualizations/donut.md) | 此視覺效果類似圓餅圖，以整體的部分或區段顯示資料。 |
| [流失](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | 流失報表可顯示在一系列預先定義的連續頁面中，訪客在哪個位置離開 (流失) 和繼續通過 (流過)。可設為最終或精確的序列 |
| [流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | 顯示客戶透過您網站和應用程式的確切路徑。 |
| [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | 自由表格不僅僅是資料表格，也是互動式視覺效果。它是工作區中資料分析的基礎。 |
| [色階分佈圖](/help/analyze/analysis-workspace/visualizations/histogram.md) | 色階分佈圖會根據量度量將訪客、瀏覽或點擊儲存在儲存區中。 |
| [橫條圖](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 顯示代表一或多個量度多個值的橫條。 |
| [折線圖](/help/analyze/analysis-workspace/visualizations/line.md) | 使用線條呈現量度，顯示一段時間內值的變化。折線圖沿x軸使用時間。 |
| [地圖](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | 可讓您建立任何量度 (包括計算量度) 的視覺化地圖。 |
| [散點圖](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | 顯示維度項目與最多三個量度之間的關係。 |
| [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 將選取的儲存格顯示為1個大數。 |
| [摘要變更](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 將所選儲存格之間的變更顯示為1個大數／百分比。 |
| [文字](/help/analyze/analysis-workspace/visualizations/text.md) | 可讓您將使用者定義文字新增至「工作區」。除了運用面板／視覺化說明外，還有助於新增其他內容至您的分析和見解 |
| [樹狀圖](/help/analyze/analysis-workspace/visualizations/treemap.md) | 以一組巢狀矩形顯示階層式 (樹狀結構) 資料。 |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) | 使用社交圈來描述最多3個區段的量度重疊。 |

## 設定 {#settings}

每個視覺效果都有各自的設定可供您管理。若要存取「 [!UICONTROL 視覺化設定]」，請按一下「 [!UICONTROL 視覺化設定] 」齒輪圖示。 部分設定包括：

| 設定 | 說明 |
| --- | --- |
| 視覺化類型 | 變更用來描述資料的視覺類型。 |
| 粒度 | 若是趨勢視覺化，您可以變更時間詳細程度（日、周、月等） 從此下拉式清單。 此變更也適用於資料來源表格。 |
| 百分比 | 以百分比顯示值。 |
| 100% 堆疊 | 此設定在堆疊區域、堆疊長條或堆疊水準長條視覺化上，可將圖表變成「100%堆疊」視覺化。 範例：![](assets/stacked_100_percent.png) |
| 可見圖例 | 可讓您隱藏「摘要編號／摘要變更」視覺化的詳細圖例文字。 |
| 項目數上限 | 可讓您限制視覺效果顯示的項目數。 |
| 將 Y 軸固定於零 | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |
| 標準化 | 強制量度為相同比例。當繪製的量度大小相差甚遠時，這會有所幫助。 |
| 顯示雙軸 | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小相差甚遠時，這會有所幫助。 |
| 顯示異常 | 顯示異常決定，以增強折線圖和自由表格。 線形視覺化中的異常偵測包括預期值（虛線）和預期範圍（著色帶）。 |

## 圖例 {#legend}

視覺化圖例可協助您將來源表格中的日期與視覺化中繪製的系列建立關聯。 圖例是互動式的——您可以按一下圖例項目，在視覺化中顯示／隱藏系列。 如果您想要簡化要視覺化的資料，這會很有幫助。

此外，您可以重新命名圖例標籤，協助您讓視覺效果更易於使用。 Note: legend editing does **not** apply to: Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

要編輯圖例標籤：

1. 以滑鼠右鍵按一下圖例標籤。
1. 按一下&#x200B;**[!UICONTROL 「編輯標籤」]**。

   ![](assets/edit-label.png)

1. 輸入新的標籤文字。
1. 按下 **[!UICONTROL Enter]** 以儲存。

以下是此主題的[影片連結](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html)。

## 右鍵功能表 {#right-click}

以滑鼠右鍵按一下視覺化標題，即可使用其他視覺化功能。 設定會依視覺化而有所不同。 部分可用設定包括：

![](assets/right-click_menu.png)

| 設定 | 說明 |
| --- | --- |
| 插入複製的面板／視覺化 | 可讓您將複製的面板或視覺化貼到（「插入」）專案內的其他位置，或貼到完全不同的專案中。 |
| 複製視覺化 | 可讓您按一下滑鼠右鍵並複製視覺化，以便將其插入專案內的其他位置，或插入完全不同的專案。 |
| [將項目下載為 CSV 檔](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-items) | 以CSV格式下載所選維度的最多50,000個維度項目。 |
| [將資料下載為 CSV 檔](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-data) | 以CSV格式下載視覺化資料來源。 |
| 複製視覺效果 | 完全複製目前的視覺效果，接著可供進行修改。 |
| 編輯描述 | 新增（或編輯）視覺化的文字說明。 |
| 取得視覺效果連結 | 可讓您將某人導向專案中的特定視覺化。 點按連結時，收件者必須先登入，才能被導向到所連結的精確視覺化。 |
| 重新開始 | （適用於流量、文氏圖、色階分佈圖）刪除目前視覺化的設定，以便從頭開始重新設定。 |

## 「建立視覺效果」圖示{#quick-viz}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row (available on hover). 這是新增視覺化的最快方式。 按一下它會提示 Analysis Workspace 教育性猜測哪個視覺效果最適合您的資料。例如，如果您已選取1列，則會建立趨勢線圖。 如果已選取3個區段行，則會建立文氏圖。

![](assets/create-visual.png)

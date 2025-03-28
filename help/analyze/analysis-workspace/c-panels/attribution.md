---
title: 歸因面板
description: 如何使用和解讀 Analysis Workspace 中的歸因面板。
feature: Attribution
role: User, Admin
exl-id: 96ce3cb9-7753-4ec0-b551-e70a1508e3b7
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: ht
source-wordcount: '692'
ht-degree: 100%

---

# 歸因面板 {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="歸因"
>abstract="使用任何維度和轉換量度，快速比較和視覺化任何數量的歸因模型"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ 面板"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="歸因面板"
>abstract="使用任何維度和轉換量度，快速比較和視覺化任何數量的歸因模型。<br/><br/>**參數&#x200B;**<br/>**管道**<br/>&#x200B;屬性依據的維度。此維度可以是行銷管道、活動或任何其他維度。<br/>**模型**<br/>&#x200B;此模型可決定如何將積分指派給接觸點。<br/>**回顧視窗**<br/>&#x200B;此設定可決定套用至每個轉換的資料歸因期間。"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ 面板"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文記錄_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 屬性面板。_<br/>_請參閱[屬性面板](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/panels/attribution)，以取得本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** 版本。_

>[!ENDSHADEBOX]

建立比較各種歸因模型的分析時，**[!UICONTROL 歸因]**&#x200B;面板是可採用的簡單方式。此面板提供您專用的工作區來使用和比較歸因模型。

Adobe Analytics 強化歸因功能，讓您可以：

* 定義付費媒體以外的歸因：任何維度、量度，管道或事件均可套用在模式上 (例如內部搜尋)，而不僅限於行銷活動。
* 不限次數利用歸因模式比較功能：動態比較任意數量的模式。
* 避免實施變更：透過報表時間處理功能和內容感知工作階段，可以建置客戶歷程內容並套用在執行階段中。
* 建構與您的歸因情境最相符的工作階段。
* 按區段劃分歸因：輕鬆比較行銷管道在任何重要區段中的效能 (例如，新客與常客、產品 X 與產品 Y、忠誠度或 CLV)。
* 跨管道檢查和多點接觸分析：使用文氏圖表和直方圖，並計算歸因結果趨勢。
* 以視覺化方式分析關鍵行銷序列活動：透過多節點流量和流失視覺效果，以視覺效果方式探究帶來轉換的路徑。
* 建立計算量度：使用任何數量的歸因配置方法。

## 使用

若要使用&#x200B;**[!UICONTROL 歸因]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 歸因]**&#x200B;面板。有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。

### 面板輸入

您可以使用下列輸入設定來設定歸因面板：

1. 新增&#x200B;**[!UICONTROL 成功量度]**&#x200B;和要歸因的&#x200B;**[!UICONTROL 管道]**。其範例包括行銷管道或自訂維度，例如內部促銷。

   ![歸因面板視窗顯示數個指定的維度和量度。](assets/attribution-panel.png)

1. 從&#x200B;**[!UICONTROL 已納入的模型]**，選取一個或多個您想要用來進行比較的[歸因模型](#attribution-models)，以及從&#x200B;**[!UICONTROL 回顧期間]**&#x200B;中選取一個您想要用來進行比較的[回顧期間](#lookback-window)。

1. 請選取「**[!UICONTROL 建置]**」，在面板中建置視覺效果。

### 面板輸出

**[!UICONTROL 歸因]**&#x200B;面板會傳回一組豐富的資料和視覺效果，用以比較指定維度和量度的歸因。

![比較指定量度和維度的歸因面板視覺效果。](assets/attr_panel_vizs.png)

### 歸因視覺效果

以下視覺效果為面板輸出的一部分。

* **總量度**：報告時間範圍內發生的轉換總數，並歸因於您指定的維度。
* **歸因比較長條圖**：以視覺效果方式比較所選維度中每個維度項目的歸因轉換。每個長條的顏色代表不同的歸因模型。
* **歸因比較表**：顯示與長條圖相同的資料，以表格的形式呈現。在此表格中選取不同的欄或列可篩選長條圖，以及面板中的其他數個視覺效果。表格的作用與 Workspace 中的其他自由格式表格相仿，可讓您新增量度、區段或劃分等元件。
* **重疊圖**：文氏圖表會顯示前三大維度項目，及其共同參與轉換的頻率。例如，重疊的泡泡圖尺寸表示人員同時接觸到兩個維度項目時發生轉換的頻率。選取相鄰自由格式表格中的其他列，可依據您的選取項目更新視覺效果。
* **效能詳細資料**：透過散佈圖視覺效果，視覺化比較最多三個歸因模型。
* **趨勢效能**：顯示排名前面的維度項目的歸因轉換趨勢。選取相鄰自由表格中的其他列，可依據您的選取項目更新視覺效果。
* **流量**：可讓您查看哪些管道最常互動，以及人員歷程中的順序。

## 歸因模型

{{attribution-models-details}}

## 回顧期間

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [建立面板](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>

<!--
# Attribution panel

The [!UICONTROL Attribution] panel is an easy way to build an analysis comparing various attribution models. It is a feature in [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) that gives you a dedicated workspace to use and compare attribution models.

>[!VIDEO](https://video.tv.adobe.com/v/23139/?quality=12)

## Create an attribution panel

1. Click the panel icon on the left.
1. Drag the [!UICONTROL Attribution] panel into your Analysis Workspace Project.

   ![New attribution panel](assets/Attribution_Panel_1.png)

1. Add a metric that you want to attribute and add any dimension to attribute against. Examples include Marketing Channels or custom dimensions, such as internal promotions.

   ![Select dimension and metric](assets/attribution_panel2.png)

1. Select the [attribution models and lookback window](../attribution/models.md) you want to compare.

1. The Attribution panel returns a rich set of data and visualizations that compare attribution for the selected dimension and metric.

   ![Attribution visualizations](assets/attr_panel_vizs.png)

## Attribution visualizations

* **Total metric**: The total number of conversions that occurred over the reporting time window. These are the conversions that are attributed across the dimension that you selected.
* **Attribution Comparison Bar**: Visually compares the attributed conversions across each of the dimension items from your selected dimension. Each bar color represents a distinct attribution model.
* **Attribution Comparison Table**: Shows the same data as the bar chart, represented as a table. Selecting different columns or rows in this table filters the bar chart as well as several of the other visualizations in the panel. This table acts similar to any other Freeform Table in Workspace - allowing you to add components such as metrics, segments, or breakdowns.
* **Overlap Diagram**: A Venn Diagram showing the top three dimension items and how often they participate jointly in a conversion. For example, the size of the bubble overlap indicates how often conversions occurred when a visitor was exposed to both dimension items. Selecting other rows in the adjacent Freeform table updates the visualization to reflect your selection.
* **Performance Detail**: Lets you to compare up to three attribution models visually using a scatter plot.
* **Trended Performance**: By default, shows the conversion performance trend by attribution model for the first dimension listed in the adjacent Freeform table. You can select different dimension rows in the Freeform table to show the trend for the selected dimensions (such as Total Revenue for each attribution model for Social Campaigns and Paid Search). Alternately, you can select cells in the columns for any metric and attribution type combinations in the Freeform table to see the trended performance by dimension value for the specified attribution models (such as Total Revenue by Marketing Channel using Last Touch and First Touch attribution).
* **Flow**: Lets you see which channels are interacted with most commonly, and in what order across a visitor's journey.

-->
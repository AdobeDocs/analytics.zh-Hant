---
description: 透過視覺效果，以視覺化方式來表示您的資料。
keywords: Analysis Workspace
title: 視覺效果概觀
feature: Visualizations
role: User, Admin
exl-id: b40aa942-4a08-4ff3-9895-e92f9a187b54
source-git-commit: 5a35d2acd428d16afff3d8e85cfb084d6a6476c4
workflow-type: tm+mt
source-wordcount: '1457'
ht-degree: 37%

---

# 視覺效果概觀

Workspace 提供許多視覺效果，可產生資料的視覺化表示法，例如長條圖、環圈圖、直方圖、折線圖、地圖、散點圖等。如果您使用 Adobe Analytics，多數視覺效果都是您所熟悉的類型。不過，Analysis Workspace 還提供視覺效果設定，以及許多具有互動功能的新或獨特的視覺效果類型。

## 視覺效果類型

Analysis Workspace 中有以下視覺效果類型：

| 視覺效果名稱 | 說明 |
| --- | --- |
| [區域](/help/analyze/analysis-workspace/visualizations/area.md)<p>![區域圖示](assets/Smock_GraphArea_18_N.svg)</p> | 類似線圖，但在線圖下方有一塊上色區域。有多個量度且以要視覺化方式表示多個量度之間交會的區域時，可使用區域圖。 |
| [長條圖](/help/analyze/analysis-workspace/visualizations/bar.md)<p>![條圖示](assets/Smock_GraphBarVertical_18_N.svg)</p> | 顯示代表一或多個量度多個值的垂直長條。 |
| [項目圖表](/help/analyze/analysis-workspace/visualizations/bullet-graph.md)<p>![專案符號圖示](assets/Smock_GraphBullet_18_N.svg)</p> | 顯示您感興趣的值與其他效能範圍 (目標) 相比較或進行測量的結果。 |
| [同類群組表格](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)<p>![同類群組表格圖示](assets/Smock_TextNumbered_18_N.svg)</p> | *`cohort`*&#x200B;是指一段指定時間內，共享相同特徵的一組人。Cohort Analysis (同類群組分析) 對保留、攪動或延遲分析很有用處。 |
| [環形圖](/help/analyze/analysis-workspace/visualizations/donut.md)<p>![環形圖示](assets/Smock_GraphDonut_18_N.svg)</p> | 此視覺效果類似圓餅圖，以整體的部分或區段顯示資料。 |
| [流失](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)<p>![流失圖示](assets/Smock_ConversionFunnel_18_N.svg)</p> | 流失報告可顯示在一系列預先定義的連續頁面中，訪客在哪個位置離開 (流失) 和繼續通過 (流過)。可以設定為最終或精確的序列 |
| [流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)<p>![流量圖示](assets/flow-icon.png)</p> | 顯示使用您網站和應用程式的正確客戶路徑。 |
| [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)<p>![自由表格圖示](assets/Smock_ViewTable_18_N.svg)</p> | 自由表格不僅是資料表格，也是互動式視覺效果。這是 Workspace 的資料分析基礎。 |
| [直方圖](/help/analyze/analysis-workspace/visualizations/histogram.md)<p>![長條圖圖示](assets/Smock_GraphHistogram_18_N.svg)</p> | 長線圖會根據量度數量，將訪客人數、瀏覽次數或點擊數放入值區內。 |
| [橫條圖](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md)<p>![橫條圖示](assets/Smock_GraphBarHorizontal_18_N.svg)</p> | 顯示代表一或多個量度多個值的橫條。 |
| [關鍵量度摘要](/help/analyze/analysis-workspace/visualizations/key-metric.md)<p>![關鍵量度圖示](assets/key-metric-icon.png)</p> | 顯示量度在單一時間範圍內的趨勢分析，或讓您比較兩個時間範圍內的量度成效。 |
| [Line](/help/analyze/analysis-workspace/visualizations/line.md)<p>![行圖示](assets/Smock_GraphTrend_18_N.svg)</p> | 使用線條呈現量度，顯示一段時間內值的變化。線形圖會延 X 軸使用時間。 |
| [地圖](/help/analyze/analysis-workspace/visualizations/map-visualization.md)<p>![地圖圖示](assets/map-icon.png)</p> | 可讓您建立任何量度 (包括計算量度) 的視覺化地圖。 |
| [散點圖](/help/analyze/analysis-workspace/visualizations/scatterplot.md)<p>![散佈圖示](assets/Smock_GraphScatter_18_N.svg)</p> | 顯示維度項目與最多三個量度之間的關係。 |
| [摘要數字](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)<p>![摘要數字圖示](assets/summary-number-icon.png)</p> | 以 1 個大數字來顯示選取的儲存格。 |
| [摘要變更](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)<p>![摘要變更圖示](assets/summary-change-icon.png)</p> | 以 1 個大數字/百分比來顯示選取儲存格之間的變化。 |
| [Text](/help/analyze/analysis-workspace/visualizations/text.md)<p>![文字圖示](assets/Smock_Text_18_N.svg)</p> | 可讓您將使用者定義文字新增至您的 Workspace。除了運用面板/視覺效果的說明之外，還有助於為您的分析和深入見解新增額外內容 |
| [樹狀圖](/help/analyze/analysis-workspace/visualizations/treemap.md)<p>![樹狀圖圖示](assets/Smock_GraphTree_18_N.svg)</p> | 以一組巢狀矩形顯示階層式 (樹狀結構) 資料。 |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md)<p>![文氏圖示](assets/venn-icon.png)</p> | 使用圓圈描繪最多 3 個區段的量度重疊。 |

## 將視覺效果新增至面板

1. 開啟您要新增視覺效果的Analysis Workspace專案。

1. 使用下列任一種方法來新增視覺效果：

   ![新增視覺效果](assets/add-visualization.png)

   * 在左側面板中，選取![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) **視覺效果**，然後將視覺效果拖曳至您要新增視覺效果的面板。

   * 在您想要新增視覺效果的面板上，選取![AddCircle](/help/assets/icons/AddCircle.svg)，然後選擇代表您要新增的視覺效果的圖示。 將滑鼠指標暫留在每個視覺效果的圖示上可檢視名稱。

   * 新增[空白面板](/help/analyze/analysis-workspace/c-panels/blank-panel.md)，然後選取您要新增的視覺效果。

   * 從您Analysis Workspace專案中現有視覺效果的內容功能表中，選取「**[!UICONTROL 複製視覺效果]**」或「**[!UICONTROL 複製視覺效果]**」。

   * 使用Workspace **[!UICONTROL 插入]**&#x200B;功能表插入視覺效果。

   * 從自由表格中的內容功能表，選取&#x200B;**[!UICONTROL 視覺化]**。 然後從子選單中選取視覺效果。 Workspace會根據表格中的目前選取專案，決定要提供哪個視覺效果，並解譯資料以建置要求的視覺效果。

## 圖例

視覺效果圖例可幫助您將來源表內的日期與視覺效果內的繪製序列產生關聯。此圖例是互動式 — 您可以選取圖例專案來顯示/隱藏視覺化效果中的序列，若要簡化資料的視覺化，這項功能相當實用。

此外，您可以重命名圖例標籤，以幫助您讓視覺效果更易使用。注意：圖例編輯&#x200B;**不**&#x200B;適用於： 樹狀圖、項目符號、累加變化/累加數、文字、自由圖形、直方圖、同類群組圖 (Cohort) 或流量圖 (Flow) 等視覺效果。

若要編輯圖例標籤：

1. 以滑鼠右鍵按一下圖例標籤。
1. 按一下&#x200B;**[!UICONTROL 「編輯標籤」]**。

   ![圖例標籤與[編輯標籤]選項。](assets/edit-label.png)

1. 輸入新的標籤文字。
1. 按下 **[!UICONTROL Enter]** 以儲存。



### 設定

可用的視覺效果設定取決於視覺效果。 下表總結了最常見的設定。 有些視覺效果確實有特定的設定。 如需詳細資訊，請參閱個別視覺效果檔案。

| 選項 | 說明 |
| --- | --- |
| **[!UICONTROL 視覺效果類型]** | 變更用來視覺化資料的視覺效果型別。 |
| **[!UICONTROL 粒度]** | 變更趨勢視覺效果的時間詳細程度。 這項變更也適用於資料來源表。 |
| **[!UICONTROL 百分比]** | 以百分比顯示值。 |
| **[!UICONTROL 100%棧疊]** | 將圖表轉換為100%棧疊的視覺效果。  僅適用於區域、長條圖和棧疊的水準長條圖視覺效果。 |
| **[!UICONTROL 可見圖例]** | 顯示圖例文字。 |
| **[!UICONTROL 限制項目數量上限]** | 限制視覺效果顯示的專案數。 選取時，定義最大專案數。 |
| **[!UICONTROL 顯示註解]** | 顯示為此視覺效果所做的註解。 |
| **[!UICONTROL 隱藏標題]** | 隱藏視覺效果的標題。 |
| **[!UICONTROL 將 y 軸固定於零]** | 強制y軸底部為零。 如果圖表上繪製的所有值都明顯大於零，則圖表預設會使y軸底部非零。 如果啟用此選項，Y軸會強製為零（且圖表會重新繪製）。 |
| **[!UICONTROL 顯示雙軸]** | 顯示兩個不同量度的左右兩側Y軸。 只有當您有兩個量度時，此選項才適用。 當繪製的量度大小不同時，雙軸會很有幫助。 |
| **[!UICONTROL 顯示 x 軸]** | 在視覺效果中顯示X軸。 |
| **[!UICONTROL 顯示 y 軸]** | 在視覺效果中顯示Y軸。 |
| **[!UICONTROL 在行]**&#x200B;上顯示槓鈴 | 在組合圖表視覺效果中的線條視覺效果上顯示槓鈴。 |
| **[!UICONTROL 標準化]** | 強制量度為相同比例。 當繪製的量度大小不同時，等比例很有幫助。 |
| **[!UICONTROL 顯示異常]** | 顯示異常偵測以強化線圖和自由格式表格。 線圖視覺效果內的異常偵測包含一個預期值 (虛線) 和一個預期範圍 (陰影帶)。 |
| **[!UICONTROL 顯示預測]** | 顯示預測值以強化線圖和自由表格。 |
| **[!UICONTROL 顯示最小值]** | 顯示視覺效果中的最小值。 |
| **[!UICONTROL 顯示最多]**&#x200B;個 | 顯示視覺效果中的最大值。 |
| **[!UICONTROL 顯示趨勢線]** | 在視覺效果中顯示趨勢線。 選取後，您可以從下拉式選單中選取趨勢線型別。 |

您可以自訂您建立的所有視覺效果設定。 如需詳細資訊，請參閱[使用者偏好設定](/help/analyze/analysis-workspace/user-preferences.md)。


## 內容選單 {#right-click}

在視覺效果標題上使用內容功能表（可透過替代選取取得，例如，使用滑鼠按一下右鍵）來存取視覺效果的其他功能。 並非所有選項都適用於所有視覺效果。

![其他視覺效果設定，其中包含顯示的滑鼠右鍵選項。 下一節將說明選項。](assets/right-click.png)

| 選項 | 說明 |
| --- | --- |
| **[!UICONTROL 插入複製的視覺化呈現]** | 將複製的視覺效果貼上（插入）專案內另一個位置或完全不同的專案中。 |
| **[!UICONTROL 將資料複製到剪貼簿]** | 將資料從視覺效果複製到剪貼簿。 |
| **[!UICONTROL 將選取專案複製到剪貼簿]** | 將視覺效果中的選取範圍複製到剪貼簿。 |
| **[!UICONTROL 將專案下載為CSV檔（*維度名稱*）]** | 將視覺效果的維度專案（最多50,000個）下載至您的本機裝置。 所選維度最多50,000個維度專案。 |
| **[!UICONTROL 複製視覺效果]** | 複製視覺效果，以便將視覺效果插入專案內另一個位置或完全不同的專案中。 |
| **[!UICONTROL 下載資料CSV]** | 將視覺效果顯示的資料下載至本機裝置。 |
| **[!UICONTROL 重複的視覺效果]** | 將視覺效果精確複製。 |
| **[!UICONTROL 編輯描述]** | 新增（或編輯）視覺效果的文字說明。 請參閱[文字](text.md)。 |
| **[!UICONTROL 取得視覺效果連結]** | 直接複製並共用視覺效果的連結。 共用連結對話方塊會顯示連結。 選取「複製」 ，將連結複製到剪貼簿。 |
| **[!UICONTROL 重新開始]** | 刪除目前視覺效果的設定，以便您從頭開始重新設定。 |


## 設定

有些視覺效果（例如同類群組表格、流失、流量等）會有一個設定對話方塊，可協助您建立視覺效果。 使用視覺效果頂端的![編輯](/help/assets/icons/Edit.svg)來存取和變更組態。

![設定窗格](assets/configuration.png)

## 視覺化

如果您不確定要挑選哪個視覺效果，請選取![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg) **[!UICONTROL 在任何自由表格列（停留時可用）中視覺化]**。 此選取範圍是新增視覺效果的最快方式。 Analysis Workspace會針對哪個視覺效果最適合您的資料做出有根據的推測。 例如，如果您選取一列，就會建立趨勢圖[線圖](line.md)。 如果您選取了三個篩選器列，則會建立[Venn](venn.md)圖表。

![快速視覺效果](assets/quick-viz.png)


<!--
## Settings {#settings}

![](assets/settings.png)

| Setting | Description |
| --- | --- |
| Visualization Type | Change the type of visual used to depict the data. |
| Granularity | For trended visualizations, you can change the time granularity (day, week, month, etc.) from this drop-down list. This change also applies to the data source table. |
| Percentages | Displays values in percentages. |
| 100% Stacked | This setting on area stacked, bar stacked or horizontal bar stacked visualizations turns the chart into a "100% stacked" visualization. Example: ![Stacked 100%](assets/stacked_100_percent.png) |
| Legend Visible | Lets you hide the detailed legend text for the Summary Number/Summary Change visualization. |
| Limit Max Items | Lets you limit the number of items that a visualization displays. |
| Anchor Y Axis at Zero | If all the values plotted on the chart are considerably above zero, the chart default will make the bottom of the y-axis NON-ZERO. If you check this box, the y-axis will be forced to zero (and it will re-draw the chart). |
| Normalization | Forces metrics to equal proportions. This is helpful when plotted metrics are of very different magnitudes. |
| Display Dual Axis | Only applies if you have two metrics - you can have a y-axis on the left (for one metric) and on the right (for the other metric). This is helpful when plotted metrics are of very different magnitudes. |
| Show Anomalies | Enhances line graphs and freeform tables by displaying anomaly detection. Anomaly detection in line visualizations includes an expected value (dashed line) and an expected range (shaded band). |

## Legend {#legend}

A visualization legend helps you to relate date in a source table to plotted series in the visualization. The legend is interactive - you can click a legend item to show/hide a series in the visualization. This is helpful if you want to simplify the data being visualized. 

Additionally, you can rename legend labels to help you make visuals more consumable. Note: legend editing does **not** apply to: Treemap, Bullet, Summary Change/Number, Text, Freeform, Histogram, Cohort or Flow visualizations.

To edit a legend label:

1. Right-click one of the legend labels.
1. Click **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Enter the new label text.
1. Press **[!UICONTROL Enter]** to save.

## Right-click menu {#right-click}

Additional functionality for a visualziation is available by right-clicking on the visualization header. Settings will vary by visualization. Some of the settings available are:

![](assets/right-click.png)

| Setting | Description |
| --- | --- |
| Insert Copied Panel/Visualization|Lets you paste ("insert") a copied panel or visualization to another place within the project, or into a completely different project. |
| Copy Visualization | Lets you right-click and copy a visualization, so that you can insert it to another place within the project, or into a completely different project. |
| [Download items as CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-items) | Download up to 50,000 dimension items for the selected dimension as a CSV. |
| [Download data as CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-data) | Download visualization data source as a CSV. |
| Duplicate Visualization | Makes an exact duplicate of the current visualization, which you can then modify. |
| Edit Description | Add (or edit) a text description for the visualization. |
| Get Visualization Link | Lets you direct someone to a specific visualization within a project. When the link is clicked, the recipient will be required to login before being directed to the exact visualization linked to. |
| Start Over | (Works for Flow, Venn, Histogram) Deletes the configuration for the current visualization so you can re-configure it from scratch. |

## Create Visual icon {#quick-viz}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row (available on hover). This the the fastest way to add a visualization. Clicking it prompts Analysis Workspace to take an educated guess at which visualization would best fit your data. For example, if you have 1 row selected, it will create a trended line graph. If you have 3 segment rows selected, it will create a Venn diagram. 

![](assets/quick-viz.png)

## Change the scale axis on visualizations

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/24708/?quality=12)

-->

---
description: 了解 Analysis Workspace 中的視覺效果和視覺效果設定。
keywords: Analysis Workspace
title: 視覺效果概述
translation-type: tm+mt
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# 視覺效果概述

工作區提供許多視覺化，可讓您產生資料的視覺化表示法，例如長條圖、環圈圖、直方圖、折線圖、地圖、散點圖等。 每個視覺化都有自己的設定可供您管理。 按一下視覺化名稱，以取得更詳細的資訊。

YouTube影片：分 [析工作區中的視覺化類型](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (2:57)

| 視覺化名稱 | 說明 |
|---|---|
| [區域](/help/analyze/analysis-workspace/visualizations/area.md) | 就像線圖，但線下有彩色區域。 有多個量度且以要視覺化方式表示多個量度之間交會的區域時，可使用區域圖。 |
| [長條圖](/help/analyze/analysis-workspace/visualizations/bar.md) | 顯示代表一或多個量度之各種值的垂直橫條。 |
| [項目圖表](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | 顯示您感興趣的值與其他效能範圍（目標）的比較或度量。 |
| [同類群組表格](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | *`cohort`* 是指一段指定時間內，共享相同特徵的一組人。例如當您想知道一個同類群組與某個品牌的互動關係時，就很適合使用同類群組分析。您可輕易看出趨勢中的變化，然後據以做出回應。 |
| [環形圖](/help/analyze/analysis-workspace/visualizations/donut.md) | 類似圓形圖，此視覺化將資料顯示為整體的部分或區段。 |
| [流失](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | 流失報表可顯示在一系列預先定義的連續頁面中，訪客在哪個位置離開 (流失) 和繼續通過 (流過)。 |
| [流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | 顯示客戶在您網站和應用程式中的路徑。 |
| [自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table.md) | 自由表格不僅是資料表格，也是互動式視覺化。 |
| [色階分佈圖](/help/analyze/analysis-workspace/visualizations/histogram.md) | 色階分佈圖類似長條圖，但是它會將數字分組到範圍（桶）中。 |
| [水準條](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | 顯示一或多個量度中代表各種值的水準橫條。 |
| [折線圖](/help/analyze/analysis-workspace/visualizations/line.md) | 表示使用行的量度，以顯示值在一段時間內的變化。 只有將時間用作維時，才能使用折線圖。 |
| [地圖](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | 可讓您建立任何量度 (包括計算量度) 的視覺化地圖。 |
| [散點圖](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | 顯示維度值與最多3個量度之間的關係。 |
| [摘要編號](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 視選取的儲存格而定，此視覺化顯示總計和摘要。 |
| [摘要變更](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | 視選取的儲存格而定，此視覺化功能會比較儲存格。 |
| [文字](/help/analyze/analysis-workspace/visualizations/text.md) | 可讓您將使用者定義的文字新增至工作區。 |
| [樹狀圖](/help/analyze/analysis-workspace/visualizations/treemap.md) | 將階層式（樹狀結構）資料顯示為一組巢狀矩形。 |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) | 可讓您拖曳最多3個區段（從元件）和一個量度以建立文氏圖。 |

## 視覺效果面板 {#section_DC07F032FBEF4046A40F7B95C28DA018}

To display the Visualizations panel, click **[!UICONTROL Visualizations]** in the side panel.

![步驟結果](assets/visualizations.png)

如果您有使用 Adobe Analytics，則會對大部分的視覺效果類型 (例如面積圖、長條圖、環圈圖和折線圖) 都很熟悉。不過，分析工作區提供視覺化設定，以及許多具有互動功能的全新或獨特視覺化類型。

## 視覺效果設定 {#section_D3BB5042A92245D8BF6BCF072C66624B}

若要存 [!UICONTROL Visualization Settings]取，請拖曳視覺化至 [!UICONTROL Freeform Panel]，然後按一下齒輪 [!UICONTROL Visualization Settings] 圖示。

>[!IMPORTANT]
>
>系統會顯示哪些視覺效果設定，需依視覺效果而定。並非所有設定都適用於所有視覺化。 此外，有些進階設定只會 **針對特定** 視覺化顯示 [，例如色階分佈](/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477)圖設定。

![](assets/visualization_settings.png)

| 設定 | 說明 |
|--- |--- |
| 百分比 | 以百分比顯示值。 |
| 100% 堆疊 | 針對堆疊區域圖/堆疊長條圖/堆疊橫條圖的設定可讓圖表以「100% 堆疊」的視覺效果方式呈現。範例： ![](assets/stacked_100_percent.png) |
| 可見圖例 | 可讓您隱藏「摘要編號／摘要變更」視覺化的篩選詳細資訊文字。 |
| 限制最大項目 | 可讓您限制視覺化顯示的項目數。 |
| 將 Y 軸固定於零 | 如果圖表上繪製的所有值都大大高於零，圖表預設值會使y軸的底部變為非零。 如果選中此框，y軸將被強制為零（並將重新繪製圖表）。 |
| 標準化 | 強制量度為相同比例。 |
| 顯示雙軸 | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。 |
| 顯示異常 | 增強折線圖和自由表格，以顯示資料異常。 |

## 「建立視覺效果」圖示{#section_9C11D9DEDC42413AA53E69A71A509DFC}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row. 當您將滑鼠指標暫留在表格列上時，此圖示將會出現。 按一下它會提示分析工作區，據知猜測哪種視覺效果最適合您的資料。 例如，如果您最多選取3個區段，則會建立文氏圖。 對於3個以上的區段，會建立長條圖。 對於其他類型的資料，它可能會建立折線圖等。

![](assets/create-visual.png)

## 右鍵視覺效果/面板功能表 {#section_05B7914D4C9E443F97E2BFFDEC70240C}

在視覺效果或面板標頭旁按一下滑鼠右鍵，可存取與圖表內容相關的設定。您可存取下列部分或全部的設定：

![](assets/right-click_menu.png)

| 設定 | 說明 |
|--- |--- |
| 插入複製的視覺化／面板 | 可讓您將複製的元素貼入（「插入」）專案內的其他位置，或貼入完全不同的專案。 |
| 複製視覺化／面板 | 可讓您按一下滑鼠右鍵並複製視覺化或面板。 |
| 複製視覺化／面板 | 請精確複製目前的視覺效果，然後您就可加以修改。 |
| 收合所有面板 | 折疊所有專案面板。 |
| 收合面板中的所有視覺效果 | 折疊此專案面板中的所有視覺化。 |
| 展開所有面板 | 展開所有專案面板。 |
| 展開面板中的所有視覺效果 | 展開此專案面板中的所有視覺化。 |
| 編輯說明 | 新增（或編輯）視覺化／面板的文字說明。 此描述會顯示在「專案 > 專案資訊和設定」中。 |
| 取得面板連結 | 可讓您將某人導向專案中的特定面板。 |
| 取得視覺化連結 | 可讓您複製並共用此連結，以直接將其他人傳送至此視覺化。 使用者必須登入。 |
| 重新開始 | （適用於流量、文氏圖、色階分佈圖）刪除目前視覺化的設定，並開啟新面板供您重新設定。 |

## 編輯圖例標籤 {#section_94F1988CB4B9434BA1D9C6034062C3DE}

您可以重新命名視覺效果圖例（流失、區域、堆疊區域、長條、堆疊長條、環圈、色階分佈圖、水準長條、堆疊水準長條、長條、散布和文氏）中的系列名稱，以協助您讓視覺效果更易於消費。

編輯圖例&#x200B;**不**&#x200B;適用於：「樹狀圖」、「項目」、「摘要變更或數字」、「文字」、「自由格式」、「色階分布圖」、「同類群組」或「流量」視覺效果。

例如，要編輯折線圖中的圖例標籤，

1. 按一下右鍵其中一個圖例標籤。
1. 按一下 **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. 輸入新的標籤文字。
1. Press **[!UICONTROL Enter]** to save.

以下是此主題的[影片連結](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)。

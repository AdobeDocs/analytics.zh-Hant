---
title: 媒體播放時間面板
description: 瞭解如何使用和解讀Analysis Workspace中的「媒體播放時間」面板。
feature: Panels
role: User, Admin
exl-id: 9268baf7-b50b-4c09-a722-7bfcd4172f15
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 90%

---

# 媒體播放時間面板 {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="媒體播放時間"
>abstract="建立一個面板來分析一段時間內的視訊觀看量，包括各種顆粒度等級以及劃分和比較的功能。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="媒體播放時間"
>abstract="分析一段時間內的視訊觀看量，選取各種詳細程度，劃分和比較。<br/><br/>**顆粒度**：選取要查看同時檢閱者的時段。<br/>**面板摘要數字 (可選)**：顯示摘要數字以及每行日期或時間詳細資料的選項。最大值將顯示尖峰播放時間的詳細資料。最小值將顯示低谷期的詳細資料。總和將顯示播放時間總計的詳細資料。<br/>**序列劃分 (可選)**：按區段、維度、維度項目或日期範圍劃分視覺效果。一次最多可檢視 10 行。劃分限於單一層級。<br/>**時間格式**：顯示視覺效果之時間格式的選項，以小時或分鐘為單位。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文記錄_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的媒體播放時間面板。_<br/>_請參閱[媒體播放時間面板](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md)，以取得本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 版本。_

>[!ENDSHADEBOX]


>[!NOTE]
>
>「媒體平均每分鐘觀眾數」面板僅適用於已購買適用於串流媒體的Adobe Analytics附加元件的客戶。
>
>請聯絡您的 Adobe 銷售代表或 Adobe 帳戶團隊以取得更多資訊。
>

**[!UICONTROL 媒體播放時間]**&#x200B;面板可進行特定期間的播放分析，提供尖峰期同時觀看人數的詳細資訊，並具備劃分和比較的能力。

在 Analysis Workspace 中，播放時間是指在特定時間點觀看您媒體串流所花的時間多寡。其中包括暫停、緩衝和開始時間。

已購買Adobe Analytics for Streaming Media附加元件的客戶可分析所花費的播放時間，以獲得寶貴的insight，進而瞭解內容品質和檢視者參與度。 並有助於疑難排解或完成數量和規模的相關規劃。

播放時間有助於了解：

* 尖峰同時發生的位置。

* 發生流失的位置。

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [媒體播放時間面板](https://video.tv.adobe.com/v/338699?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]

## 使用

若要使用&#x200B;**[!UICONTROL 媒體播放時間]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 媒體播放時間]**&#x200B;面板。有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 確保您為面板選取報表套裝，該面板具有從Adobe Analytics for Streaming Media附加元件設定的元件。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。


### 面板輸入

您可使用以下這些輸入設定來設定「媒體播放時間」面板。

| 設定 | 說明 |
|---|---|
| 面板日期範圍 | 面板的日期範圍預設為「今天」。您可將其編輯為一次檢視一天或多個月。<br>此視覺效果僅限 1440 列資料 (例如，以分鐘為最小顆粒度測量 24 小時)。如果日期範圍和顆粒度組合結果超過 1440 行，則顆粒度會自動更新以符合完整的日期範圍。 |
| 顆粒度 | 顆粒度的預設為「分鐘」。<br>此視覺效果僅限 1440 列資料 (例如，以分鐘為最小顆粒度測量 24 小時)。如果日期範圍和顆粒度組合結果超過 1440 行，則顆粒度會自動更新以符合完整的日期範圍。 |
| 面板摘要數字 | 若要查看播放時間的日期或時間詳細資訊，可使用摘要數字。「最大值」會顯示高峰期同時觀看人數的詳細資訊。「最小值」會顯示低谷期的詳細資訊。「總和」會加總選取範圍所花費的總播放時間。面板預設僅顯示「最大值」，但您可加以改變，以顯示「最小值」、「總和」或三者的任何組合。<br>如果您使用劃分功能，每項會顯示累加數。 |
| 序列劃分 | 您可視需要將視覺效果根據篩選器、維度、維度項目或日期範圍劃分。<p>- 一次最多可檢視 10 行。劃分限於單一層級。</p><p>- 拖曳一個維度時，系統將根據選取面板日期範圍自動選取最上層的維度項目。</p>- 若要比較日期範圍，請將 2 個或多個日期範圍拖放到序列劃分篩選器。 |
| 時間格式 | 您可以`Hours:Minutes:Seconds` (預設) 或`Minutes` (會以整數顯示，0.5 會四捨五入) 來檢視播放時間。 |
| 日期序列顯示 | 如果您選定至少兩個日期範圍篩選器進行序列劃分，您會看到可選取覆蓋 (預設) 或循序的選項。覆蓋會顯示具有常見 x 軸起點的線條，因此它們會平行執行，而序列會顯示具有特定 x 軸起點的線條。如果資料排列整齊（例如，篩選器1在下午8:44結束，篩選器2在下午8:45開始），則這些行會依序顯示。 |


![媒體播放時間的預設視圖。](assets/mpts_default_view.png)

### 面板輸出

「媒體播放時間」面板會返回折線圖和摘要數字，以包括播放時間最大值、最小值和/或總和的詳細資訊。面板頂端會提供一個摘要行，為您提示您所選取的面板設定。

可隨時選取「![編輯媒體播放時間面板](/help/assets/icons/Edit.svg)」，以編輯和重建面板。

如果您選取序列劃分、線圖上的一條線，則每項會顯示累加數：

![媒體播放時間輸出顯示折線圖和摘要。](assets/mpts_outputs1.png)

### 資料來源

此面板中能使用的唯一量度是「播放時間」。

| 量度 | 說明 |
|---|---|
| 播放時間 | 在選取的顆粒度期間觀看內容的總計`hours:minutes:seconds` (或`minutes`)，包括暫停、緩衝和開始時間。 |

## 常見問題

| 問題 | 回答 |
|---|---|
| 自由格式表格在哪裡？我如何可看到資料來源？ | <p></p><p>本檢視中無法使用自由格式表格。若要下載資料來源，請從折線圖中的內容選單中選取下載 CSV 檔案的選項。</p> |
| <p>為什麼我的顆粒度改變了？</p> | <p>此視覺效果僅限 1440 列資料 (例如以分鐘為最小顆粒度測量 24 小時)。如果日期範圍和顆粒度組合結果超過 1440 列，則顆粒度會自動更新以符合完整的日期範圍。</p><p></p><p>從較大的日期範圍變更至較小的日期範圍時，一旦日期範圍變更，顆粒度將更新至允許的最低顆粒度。若要檢視更高的顆粒度，請編輯面板並重建。</p> |
| <p></p><p>我該如何比較影片名稱、篩選器、內容類型和更多內容？</p> | <p>若要在單一視覺效果中比較這些內容，可將篩選器、維度或特定維度項目拖動至序列劃分篩選器內。</p><p></p><p>此檢視限於 10 項劃分。若要檢視超過 10 項，您必須使用多個面板。</p> |
| 我如何比較日期範圍？ | 若要比較單一視覺效果中的日期範圍，可拖動 2 個或多個日期範圍以使用系列劃分。這些日期範圍會覆寫面板日期範圍。 |
| 如何改變視覺效果類型？ | <p></p><p>此面板僅允許進行時間序列的線圖視覺效果。</p> |
| 我是否可執行異常偵測？ | <p></p><p>否。 異常偵測不適用於此面板。</p> |


>[!MORELIKETHIS]
>
>[建立面板](/help//analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>[媒體平均分鐘觀眾數面板](average-minute-audience-panel.md)
>[媒體同時檢視者面板](media-concurrent-viewers.md)
>

<!--
# Media Playback Time Spent panel

In Analysis Workspace, Playback Time Spent is the amount of time spent viewing your media streams at a specific point in time. It includes pause, buffer, and time to start.

The Media Playback Time Spent panel enables analysis of playback over time, with details on peak concurrency and the ability to break down and compare. 

Customers who have purchased the Streaming Media Collection Add-on can analyze playback time spent to gain valuable insight into the quality of content and viewer engagement, and to help when troubleshooting or planning for volume or scale.

Playback Time Spent can help you understand:

* Where peak concurrency occurred

* Where drop-offs occurred 

Following is a video overview of this panel:

>[!VIDEO](https://video.tv.adobe.com/v/338699)

## Use the Media Playback Time Spent panel

1. Go to a report suite with streaming media components enabled. 
1. Select the panel icon on the far-left, then drag the panel into your Analysis Workspace project.
1. Continue with the following sections to customize the Media Playback Time Spent panel

   * [Panel Inputs](#panel-inputs)
   * [Panel Output](#panel-output)

## Panel Inputs {#Input}

You can configure the Media Playback Time Spent panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today. You may edit it to view a single day or many months at a time.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers|To see date or time details for playback time spent, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough. Sum adds up the total playback time spent for the selection. The panel default shows Maximum only, but you can change it to show Minimum, Sum, or any combination of the three.<br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown|Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges.<p>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.</p><p>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.</p>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|
|Time format|You can view the playback time spent in either `Hours:Minutes:Seconds` (default) or in `Minutes` (which is displayed in whole numbers, rounded up at .5). |
|Date sequence display|If you've placed at least two date range segments as series breakdowns you'll see the option to select either overlay (default) or sequential. Overlay will display the lines with a common x-axis start so that they run in parallel, while sequential will display the lines with their specific x-axis start. If the data lines up (for example, segment 1 ends at 8:44 pm and segment 2 starts at 8:45 pm), then the lines will show in sequence. |

## Default view

![Default view](assets/mpts_default_view.png)

## Panel Output {#Output}

The Media Playback Time Spent panel returns a line chart and summary numbers to include details for the maximum, minimum, and/or sum of playback time spent. At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![media playback time spent output](assets/mpts_outputs1.png)

### Data Source

The only metric that can be used in this panel is Playback Time Spent.

|Metric|Description|
|---|---|
|Playback Time Spent|Total `hours:minutes:seconds` (or `minutes`) of content viewed during the selected granularity including pause, buffer, and time to start.|

## FAQs

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?|The Freeform table is not available in this view. You can download the data source by right-clicking on the line chart and downloading the CSV ﬁle.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range. <p>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.</p>|
| How do I compare video names, segments, content types, etc?| To compare these in a single visualization, drag segments, dimensions, or speciﬁc dimension items in the series breakdown ﬁlter.The view is limited to 10 breakdowns. To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges. These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No. Anomaly detection is not available for this panel.|

-->

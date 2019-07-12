---
title: Adobe Analytics中的對象報表
description: 瞭解如何使用分析工作區建立讀者型報表。
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# 對象報表

「對象」報表顯示瀏覽您網站的訪客類型相關資訊。

此頁面假設使用者具備使用分析工作區的基本知識。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## 作用中的使用者

「活動中的使用者」會顯示您的網站在前1、7、14或28天內的累積使用者數量。雖然Adobe沒有Google Analytics中使用的精確計算，但您可以使用量度獨特訪客，根據選取的日期範圍，查看使用者對您網站的重復計算計數。

若要取得獨特訪客的折線圖：

1. 按一下左側的「視覺效果」圖示，並將「線條視覺效果」拖曳至空白自由表格上方的工作區上。
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled &#39;Drop a Metric here&#39;.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) 位於現有的日期維度標題之上。

See [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## 期限值

期限值是需要在兩個平台上額外實施的功能。Adobe建議您與實施顧問合作取得此資料。

## 同類群組分析

世代分析顯示相同使用者回訪網站的頻率。

若要建立同類群組表格：

1. 按一下左側的「視覺效果」圖示，然後拖曳同類群組表格視覺化至工作區。
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. 按一下「建立」。

See [Cohort Analysis](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## 對象

Google Analytics中的「對象」報表需要設定對象。觀眾也需要Adobe Audience Manager中的設定。如需詳細資訊，請參閱Adobe Audience Manager使用指南。

## User Explorer

「使用者總管」報表可讓分析者透過匿名識別碼檢視個別瀏覽。Adobe不會將資料饋送以外的後端識別碼浮出水面，這是點擊層級資料的來源。

* 如果在Analysis工作區中需要此資料，可以與實施顧問合作，將匿名唯一識別碼Cookie值傳遞至eVar。請注意，這僅適用於較小的實施，包括每個月不超過1000000個獨特訪客的實施。
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](../../../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.

## 人口統計與興趣報告

人口統計和興趣資料提供有關網站使用者年齡、性別和興趣的資訊。該資料由Google透過其跨網站追蹤能力收集。

人口統計和興趣資料不會自動由Adobe收集。不過，如果您的組織取得此資料，您可以使用Adobe Experience Cloud Platform中的「客戶屬性」。它可完全控制由屬性組織資料，不僅限於人口統計或興趣。

如需詳細資訊，請參閱客戶屬性說明。

## 地理-語言

地理語言報表會依據訪客瀏覽器中的語言設定顯示網站流量。

若要建立語言報表：

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](../../../components/c-variables/dimensionslist/reports-languages.md) dimension in the Components user guide for more information.

## 地理-位置

地理位置報告提供全球地圖檢視，依國家區分資料。

若要建立地理位置報表：

1. 按一下左側的「視覺效果」圖示，將地圖視覺化拖曳至空白自由表格上方的工作區上。
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled &#39;Add Metric&#39;.
3. 按一下「建立」。

如果表格另外也需要表格：

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See [Geosegmentation](../../../components/c-variables/dimensionslist/reports-geosegmentation.md) dimensions in the Components user guide for more information.

## 行為-新功能與舊版

新的與回訪報表可簡化第一個作業(新瀏覽)與後續作業(回訪)的檢視。

若要建立新的回訪報表：

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;. Note that **First Time Visits** is a segment, while Workspace typically uses dimensions to represent rows.
2. Locate the **Return Visits** segment and drag it on top of the Segments row header. 這會將區段新增為「首次瀏覽」下方的維度，以便進行簡單比較。
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

如果也需要折線圖：

1. 按一下左側的視覺效果圖示，並拖曳「Line」視覺化至自由表格上方的工作區上。
2. 在自由表格中每一列上，使用ctrl+ click(Windows)或cmd+ click(Mac)來強調它們。這可讓這兩種趨勢出現在線條視覺效果中。
3. 按一下線條視覺效果左上角的小圓角圓點，然後按一下核取方塊「鎖定選取範圍」。

## 行為-頻率與最近一次

The frequency &amp; recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](../../../components/c-variables/dimensionslist/reports-visitor-number.md) dimension in the Components user guide for more information.

## 行為-參與

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](../../../components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dimension in the Components user guide for more information.

## 技術-瀏覽器與作業系統

「瀏覽器與作業系統」報表有多個主要維度可用。

* **「瀏覽器** 」主要維度也可用於分析工作區中。
* **「作業系統** 」主要維度也可用於分析工作區中。
* **「螢幕解析度** 」主要維度可在「分析工作區」中做為 **「監視器解析度** 」維度使用。
* **「螢幕色彩** 」主要維度可在「分析工作區」中做為 **「色彩深度** 」維度使用。
* **Adobe Analytics無法使用Flash版本** 主要維度，但是有需要時，可由eVar收集此資料。

1. 在元件選單中，找出上述所要的維度，並將它拖曳至標示為「拖曳到此處」的大型自由表格區域。
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

如需詳細資訊，請參閱元件使用指南中的下列頁面：

* [瀏覽器](../../../components/c-variables/dimensionslist/reports-browsers.md)
* [作業系統 ](../../../components/c-variables/dimensionslist/reports-operating-system.md)
* [監視器解析度](../../../components/c-variables/dimensionslist/reports-technology.md)
* [色彩深度](../../../components/c-variables/dimensionslist/reports-color-depth.md)

## 技術-網路

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](../../../components/c-variables/dimensionslist/reports-domains.md) dimension in the Components user guide for more information.

## 行動-概觀

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. 請注意，「其他」值等同於桌面流量。

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device Type](../../../components/c-variables/dimensionslist/reports-device-types.md) dimension in the Components user guide for more information.

## 行動-裝置

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device](../../../components/c-variables/dimensionslist/reports-devices.md) dimension in the Components user guide for more information.

## 自訂

自訂報表是依實施定義。與組織的Analytics管理員及/或實施顧問合作，以解譯這些報告。Typically an organization maintains a [Solution Design Document](../../../implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## 基準基準

基準報表可讓您查看資料的Facet與行業平均值的比較。Adobe目前並未與客戶分享基準資料。

## 使用者流量

流量報告可在兩個平台上使用。若要建立流量報表：

1. 按一下左側的視覺效果圖示，並拖曳流量視覺化至自由表格上方的工作區上
2. Locate the **Pages** dimension, then click the Arrow icon to reveal page values. 維度值是黃色的。
3. 找出所要的頁面值，並將其拖曳至中心中標示為「維度或項目」的空格
4. 此流量報告為互動式報表。按一下任何值，將流量展開至後續或先前頁面。使用右鍵功能表展開或收合欄。也可以在相同的流量報表中使用不同維度。

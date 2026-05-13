---
description: 了解有關您可以使用現有量度來建立的計算量度。
keywords: 計算量度
title: 計算量度概觀
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
TQID: https://experienceleague.adobe.com/3bZdi3MZ8Q5MibUfwOlO1CmumXTqlWxBH6hy35M9tUk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 75%

---

# 計算量度概觀

計算量度為您可以利用現有量度建立的自訂量度。

計算量度是您可從現有量度建立的自訂量度。 計算量度提供一種靈活的方式來建置、管理和策劃自訂量度，使您能夠分析資料而無需變更實施。

每個[!DNL Analytics]套件都有計算量度可以使用，不過Experience Cloud的Adobe Analytics Foundation Pack僅限於基本計算量度，包括[格式型別（小數、時間、百分比、貨幣）](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)、[配置變更（預設、線性、參與率等）](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)、[量度型別（標準、總計）](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)和[基本運運算元](workflow/c-build-metrics/cm-build-metrics.md#operators) （加、減、乘、除）。


請參閱 [Adobe Analytics 產品說明](https://helpx.adobe.com/tw/legal/product-descriptions/adobe-analytics.html)，以了解更多資訊。

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/calculated-metrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 建立 [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 異常偵測]以及[!UICONTROL 貢獻度分析]的[各個量度](/help/components/calculated-metrics/workflow/cm-workflow.md)。
* [建立區段量度](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)，不需要變更實作，可以從報告執行時間推導得出。 例如，您可以建立「*新訪客*」量度，計算這是其首個工作階段的人員數量。

* 在各個報告套裝之間[共用量度](/help/components/calculated-metrics/workflow/cm-sharing.md)。 這表示所有新建立的量度皆會套用至相同登入公司的所有報告套裝。

* [結合統計函數](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)，協助您更清楚說明資料。 例如，您可以計算報告中的項目數或為每個項目加入標準差數量。

## 限制

部分 [!DNL Analytics] 功能不允許使用計算量度：

* Analysis Workspace 中的「副產品」
* [!UICONTROL Analysis Workspace 中的「同類群組分析」]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 區段]
* [!DNL Target] 的 [!DNL Analytics]


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [計算量度](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics){target="_blank"}的示範影片。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [區段的分段計算量度](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"}示範影片。

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[建立量度](/help/components/calculated-metrics/workflow/cm-workflow.md)
>[建立量度](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)
>[使用函數](/help/components/calculated-metrics/workflow/c-build-metrics/cm-using-functions.md)
>

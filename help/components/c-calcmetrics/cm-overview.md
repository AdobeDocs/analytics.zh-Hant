---
description: 計算和進階計算量度為您可從現有量度建立的自訂量度。
keywords: 計算量度和進階計算量度
title: 計算和進階計算量度
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 9714863374052e257e1d6349c442fc74182a0a2f
workflow-type: ht
source-wordcount: '365'
ht-degree: 100%

---

# 計算和進階計算量度

計算和進階計算量度為您可從現有量度建立的自訂量度。

我們的計算量度工具可讓您以極為靈活的方式建立、管理和規劃量度。無論您是行銷人員、產品經理或分析人員，不需變更 [!DNL Analytics] 實作就能詢問資料相關問題。每個 [!DNL Analytics] 套裝中可用的自訂量度為：

* Adobe [!DNL Analytics] Foundation：計算
* [Adobe Analytics Select](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html)：計算 + 進階計算
* [Adobe Analytics Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/prime.html)：計算 + 進階計算
* [Adobe Analytics Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/ultimate.html)：計算 + 進階計算

以下為計算量度和進階計算量度功能比較：

| Builder 選項 | 計算量度 | 進階計算量度 |
|---|---|---|
| [格式類型 (小數、時間、百分比、貨幣)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | 是 | 是 |
| [歸因變更 (預設、線性、參與率等)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| [量度類型 (標準、總計)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| 基本運算元 (加、減、乘、除) | 是 | 是 |
| [套用區段](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | 無 | 是 |
| [基本函數 (計數、abs 值、平均值等)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | 無 | 是 |
| [進階函數 (迴歸、if/then、t 分數等)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | 無 | 是 |

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 在 [!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 異常偵測] 以及 [!UICONTROL 貢獻分析]內建立量度。
* 無需變更實作，即可建立衍生自報告執行時間的區段量度。因為這些量度的根據是區段，所以可檢視其歷史資料。

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [計算量度](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]

* 在報表套裝間共用量度。這表示所有新建立的量度都會套用至相同登入公司的所有報表套裝。
* (僅限進階計算量度) 量度上的區段。例如，您可以建立「新訪客」的量度，計算第一次進行工作階段的人員數量。

* (僅限進階計算量度) 納入統計函數以協助您更妥善地說明資料。例如，您可以計算報告中的項目數或新增每個項目的標準差數字。


## 限制

部分 [!DNL Analytics] 功能可讓您使用事件，但無法使用計算量度：

* Analysis Workspace 中的「副產品」
* [!UICONTROL Analysis Workspace 中的「同類群組分析」]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 區段]
* [!DNL Target] 的 [!DNL Analytics]


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [計算量度](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [區段的分段計算量度](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"}示範影片。

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->
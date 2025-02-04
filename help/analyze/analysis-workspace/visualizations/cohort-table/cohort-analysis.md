---
title: 什麼是「同類群組分析」？這又是如何運作的？
description: 透過「同類群組分析」，深入了解使用客群資料，並分成相關的群組。了解 Analysis Workspace 中的「同類群組分析」。
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 33%

---

# 同類群組表格概觀 {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="同類群組表格"
>abstract="建立同類群組視覺效果，根據事件的完成情形將使用者分組，並分析一段時間內的持續參與度和流失情況。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="同類群組表格"
>abstract="根據事件的完成情形將使用者分組，然後分析他們在一段時間內的持續參與度及流失情況。<br/><br/>**參數&#x200B;**<br/>**包含條件**：這些元件用以定義初始訪客同類群組。<br/>**回訪條件**：這些元件用以判斷訪客是否已回訪。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文會記錄_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的同類群組表格。_<br/>_檢視此文章的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[同類群組表格](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis)。_

>[!ENDSHADEBOX]



*同類群組*&#x200B;是指一段指定時間內，共用相同特徵的一組人。 例如，當您想要瞭解同類群組與品牌的互動關係時，![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同類群組表格]**&#x200B;視覺效果就很實用。 您可輕易看出趨勢中的變化，然後據以做出回應。(網路上有[!UICONTROL 同類群組分析]的解釋可供參考，例如 [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis)。)

建立同類群組報表後，您可以組織其元件 (特定的維度、量度和篩選器)，接著將同類群組報表與他人共用。 請參閱[監管與共用](/help/analyze/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同類群組表格]可以做的事情範例：

* 推行專為刺激所需動作的促銷活動。
* 在客戶生命週期的正確時間點轉移行銷預算。
* 識別何時結束試用或優惠方案，以最大化價值。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。

[!UICONTROL 同類群組表格]適用於具有[!UICONTROL Analysis Workspace]存取許可權的所有Customer Journey Analytics客戶。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace中的同類群組分析](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL 同類群組分析]不支援無法篩選的量度（包括計算量度）、非整數量度（例如收入）或發生次數。 只有可以在篩選器中使用的量度才能用於[!UICONTROL 同類群組分析]，而且這些量度一次只能增加1。

Customer Journey Analytics中的同類群組表格支援雙向（或任何數值型）量度。 例如，Purchase.Value (a double)可作為包含/傳回量度使用。 此外，所有透過Analytics Source Connector傳入Adobe Experience Platform的量度也是兩倍。

## 同類群組表格功能

以下幾節將說明同類群組分析功能，這些功能可讓您對您正在建立的同類群組進行微調控制。

如需建立同類群組及執行[!UICONTROL 同類群組分析]報表的詳細資訊，請參閱[設定同類群組表格](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### [!UICONTROL 保留率]資料表

[!UICONTROL 保留率]同類群組表格會傳回人員：每個資料儲存格顯示該同類群組中，在該時段內執行了動作的原始人數和百分比。 您可以包含最多 3 個量度和最多 10 個篩選器。

![顯示同類群組中人員的單位和百分比的演繹版同類群組報告。](assets/retention-report.png)

### [!UICONTROL 流失率]資料表

[!UICONTROL 流失率]同類群組表格與保留率表格相反，會顯示在一段時間內離開或從未符合約類群組回傳條件的人員。 您可以包含最多 3 個量度和最多 10 個篩選器。

![顯示不符合約類群組回傳條件之人員的單位與百分比的流失率表格。](assets/churn-report.png)

### [!UICONTROL 滾動式計算]

您可以根據上一欄計算保留率或流失率，而非根據「包含」欄（即滾動式計算）。

![同類群組保留率報表顯示根據上一欄資料進行的計算。](assets/retention-report-rolling.png)

### [!UICONTROL 延遲]資料表

延時表格會衡量包含事件發生前後的經過時間。 測量延遲是進行事前和事後分析的絕佳工具。 **[!UICONTROL 包含]**&#x200B;欄位於表格的中央，包含事件前後的時段會顯示於兩側。

![顯示事件前後經過時間的同類群組報告。](assets/retention-report-latency.png)

### [!UICONTROL 自訂維度]同類群組

您可以根據選取的維度建立同類群組，而非根據以時間為主的同類群組（預設）。 使用如[!UICONTROL 城市地理]、[!UICONTROL 行銷管道]、[!UICONTROL 行銷活動]、[!UICONTROL 產品]、[!UICONTROL 頁面]、[!UICONTROL 地區]等維度，或任何其他維度，來顯示保留率有何變更。 根據這些維度的不同值。

![顯示自訂報表的同類群組報表，其中包含已選取的維度，而非預設的時間型同類群組。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[設定同類群組表格](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>



<!--
A *`cohort`* is a group of people sharing common characteristics over a specified period. [!UICONTROL Cohort Analysis] is useful, for example, when you want to learn how a cohort engages with a brand. You can easily spot changes in trends, then respond accordingly. (Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

After creating a cohort report, you can curate its components (specific dimensions, metrics, and segments), then share the cohort report with anyone. See [Curate and Share](/help/analyze/analysis-workspace/curate-share/curate.md).

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* Launch campaigns designed to spur a desired action.
* Shift marketing budget at exactly the right time in the customer lifecycle.
* Recognize when to end a trial or an offer, in order to maximize value.
* Gain ideas for A/B testing in areas such as pricing, upgrade path, and so on.

[!UICONTROL Cohort Analysis] is available for all Adobe Analytics customers with access rights to [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cohort analysis in Analysis Workspace](https://video.tv.adobe.com/v/25965?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] does not support non-segmentable metrics (including calculated metrics), non-integer metrics (such as Revenue), or Occurrences. 
>
>Only metrics that can be used in segments can be used in [!UICONTROL Cohort Analysis], and they can only be incremented by >1 at a time. 

## Cohort Analysis capabilities

The following sections describe Cohort Analysis features that allow for fine-tuned control over the cohorts you are building.

For more detailed information about creating a cohort and running a [!UICONTROL Cohort Analysis] report, see [Configure a Cohort Analysis report](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### [!UICONTROL Retention] Table

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. You can include up to 3 metrics and up to 10 segments.

![](assets/retention-report.png)


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calculate rolling retention](https://video.tv.adobe.com/v/25962?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



### [!UICONTROL Churn] Table

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. You can include up to 3 metrics and up to 10 segments.

![](assets/churn-report.png)

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Churn analysis](https://video.tv.adobe.com/v/25966?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


### [!UICONTROL Rolling Calculation]

Lets you calculate retention or churn based on the previous column, not the included column.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Table

Measures the time that has elapsed before and after the inclusion event occurred. This is an excellent tool for pre/post analysis. The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL Custom Dimension] Cohort

Create cohorts based on a selected dimension, and not time-based cohorts, which are the default. Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

-->

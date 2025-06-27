---
title: 同類群組表格概觀
description: 瞭解如何深入瞭解您的對象資料，並透過同類群組分析將這些資料分成相關的群組。 在Analysis Workspace中使用同類群組分析。
feature: Visualizations
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 90%

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

_本文記錄_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 中的同類群組表格。_<br/>_請參閱[同類群組表格](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis)，以取得本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** 版本。_

>[!ENDSHADEBOX]



*同類群組*&#x200B;是指一段指定時間內，共用相同特徵的一組人。例如，當您想要了解同類群組與某個品牌的互動關係時，![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同類群組表格]** 視覺效果非常實用。您可輕易看出趨勢中的變化，然後據以做出回應。(網路上有[!UICONTROL 同類群組分析]的解釋可供參考，例如 [Cohort Analysis 101](https://zh.wikipedia.org/wiki/Cohort_analysis)。)

建立同類群組報表後，您可以組織其元件 (特定的維度、量度和篩選器)，接著將同類群組報表與他人共用。 請參閱[監管與共用](/help/analyze/analysis-workspace/curate-share/curate.md)。

[!UICONTROL 同類群組表格]的用途範例：

* 推行專為刺激所需動作的促銷活動。
* 在客戶生命週期的正確時間點轉移行銷預算。
* 識別何時終止試用版或產品建議，以價值最大化。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。

[!UICONTROL 同類群組表格]適用於具有[!UICONTROL Analysis Workspace]存取許可權的所有Adobe Analytics客戶。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的同類群組分析](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL 同類群組分析]不支援無法篩選的量度 (包括計算量度)、非整數量度 (例如收入) 或發生次數。僅可在篩選器中使用的量度才能用於[!UICONTROL 同類群組分析]，且這些量度一次只能遞增 > 1 的值。

Adobe Analytics中的同類群組表格支援雙向（或任何數值）量度。 例如，Purchase.Value (雙精度) 可用於包含/回報量度。此外，透過 Analytics 來源連接器傳遞至 Adobe Experience Platform 的所有量度皆為雙精度。

## 同類群組表格功能

下列區段說明同類群組分析功能，可對您正在建立的同類群組進行微調控制。

有關建立同類群組和執行[!UICONTROL 同類群組分析]報告的更多資訊，請參閱[設定同類群組表格](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### 保留率表格

[!UICONTROL 保留率]同類群組表格回傳人數：每個資料儲存格顯示此同類群組中，在該時段內執行動作的原始人數和百分比。您可以包含最多 3 個量度和最多 10 個篩選器。

![保留率同類群組報告顯示同類群組中的人員單位和百分比。](assets/retention-report.png)

### 流失率表格

[!UICONTROL 流失率]同類群組表格和保留率表格相反，會顯示在特定時間內離開或從未符合同類群組回傳條件的人員。您可以包含最多 3 個量度和最多 10 個篩選器。

![流失率表格顯示不符合同類群組回傳標準的人員單位和百分比。](assets/churn-report.png)

### 滾動式計算

您可以根據前一欄而非將欄納入來計算保留率或流失率，稱為滾動式計算。

![同類群組保留率報告顯示根據資料前一欄的計算。](assets/retention-report-rolling.png)

### 延遲表

延遲表格測量包括事件發生前後經過的時間。測量延遲是進行事前/事後分析的絕佳工具。**[!UICONTROL 包含]**&#x200B;欄位於表格的中央，包含事件前後的時段會顯示於兩側。

![同類群組報告顯示事件前後經過的時間。](assets/retention-report-latency.png)

### 自訂維度同類群組

您可以根據選取的維度建立同類群組，而非根據以時間為基礎的同類群組 (預設)。使用以下維度，例如[!UICONTROL 城市地理]、[!UICONTROL 行銷管道]、[!UICONTROL 行銷活動]、[!UICONTROL 產品]、[!UICONTROL 頁面]、[!UICONTROL 地區]，或任何其他維度來顯示保留率如何變更。根據這些維度不同的值。

![同類群組報告顯示使用選取維度的自訂報告，而非預設以時間為基礎的同類群組。](assets/retention-dimensions.png)

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

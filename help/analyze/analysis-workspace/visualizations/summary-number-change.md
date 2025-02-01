---
description: 使用「摘要數字」和「摘要變更」視覺效果來呈現專案中的重要資料點。
title: 摘要數字和摘要變更
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: 5a35d2acd428d16afff3d8e85cfb084d6a6476c4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 49%

---

# [!UICONTROL 摘要數字]和[!UICONTROL 摘要變更]

_本文記錄了_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;中的摘要編號和摘要變更視覺效果。_<br/>_檢視此文章的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版本的[摘要編號和摘要變更](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change)。_


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [摘要數字與摘要變更視覺效果](https://video.tv.adobe.com/v/335564/?quality=12){target="_blank"}。

>[!ENDSHADEBOX]


## [!UICONTROL 摘要數字]視覺效果 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="摘要數字"
>abstract="建立顯示總計和小計的視覺效果。"

<!-- markdownlint-enable MD034 -->


使用![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 摘要變更]**&#x200B;視覺效果來顯示兩個數字間的差異（變更）。<!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

此視覺效果的運作方式如下：

* 如果未選取儲存格，則會比較欄中前兩個儲存格的值。
* 如果選取一個儲存格，由於與自身比較儲存格的值，因此會顯示 0。
* 如果選取兩個儲存格，會取第一個選取的儲存格為分子，第二個選取的儲存格為分母。
* 如果選取超過兩個儲存格，僅會比較前兩個選取的儲存格。
* 如果選取某個範圍中的儲存格，會比較該範圍第一個與最後一個選取的儲存格。
* 如果選取欄，會就第一個值的本身進行比較，顯示變更為 0。


![摘要變更視覺效果顯示兩個數字間的差異。s](assets/summary-change.png)


作為視覺效果設定的一部分，可以使用特定的&#x200B;**[!UICONTROL 摘要變更選項]**。

| 選項 | 定義 |
|--- |--- |
| **[!UICONTROL 顯示百分比變更]** | 顯示2個數字之間的百分比變化。 |
| **[!UICONTROL 顯示原始差異]** | 顯示2個數字之間的原始差異。 您也可以縮簡值，使用此選項顯示最多小數點後 3 位。 |
| **[!UICONTROL 縮簡值]** | 選取&#x200B;**[!UICONTROL Abbreviate value]**&#x200B;以智慧地縮簡變更的值。 選取時，輸入數字以定義縮寫金額。 例如：<br/><table><tr><td>**原始值**</td><td>**縮寫值**</td><td>**結果**</td></tr><tr><td>12,011,141.25美元</td><td>未選取</td><td  align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`0`</td><td align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td> 已選取，設定為`1`</td><td  align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`2`</td><td align="right">1201萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`3`</td><td align="right">1201.1萬美元</td></tr></table> |

>[!MORELIKETHIS]
>
>[將視覺效果新增至面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺效果內容功能表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

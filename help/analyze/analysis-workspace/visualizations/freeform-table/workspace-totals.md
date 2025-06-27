---
description: 瞭解Analysis Workspace中自由格式表格的總計計算方式。
title: 總計
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 81%

---

# 總計 {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="總量"
>abstract="具靜態列的表格或劃分不支援全部總計。"

在自由表格中，每個劃分層級都會顯示總列數，當中會顯示兩個總計數字：

![自由格式表醒目顯示總計和表格總計。](assets/total-row.png)

* **[!UICONTROL 資料表總計]** ➊ — 此總計通常等於[!UICONTROL 總計]或是其子集。 總計反映的是在自由表格中套用的任何表格篩選條件，包括[!UICONTROL 「不包含任何項目」]選項。
* **[!UICONTROL 總計]** （**[!UICONTROL 個，共]**&#x200B;個&#x200B;*數字*） ➋ — 此總計代表已收集的所有事件。 在面板層級或自由格式表格中套用篩選器時，這個總計會進行調整，以反映出符合篩選條件的所有事件。




## 顯示總計

![「設定」](/help/assets/icons/Setting.svg)**[!UICONTROL 「欄設定」]**&#x200B;下方有「**[!UICONTROL 顯示總計]**」和「**[!UICONTROL 顯示總量]**」選項。如果未選中這些設定，總數將從表格中刪除，在總數不合理情況下可能必須這樣做。


[靜態列](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)總計的行為方式不同，且須使用![「設定」](/help/assets/icons/Setting.svg)**[!UICONTROL 「列設定」]**&#x200B;來控制。

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 顯示目前行數的總和作為總數]** | 顯示表格中的客戶端行數總和。此總和&#x200B;**不會**&#x200B;刪除如工作階段或人數等重複量度。 |
| **[!UICONTROL 顯示總量]** | 顯示伺服器端總數。此總和會刪除如工作階段或人數等重複量度。 |

請參閱「[自由表格中的動態與靜態維度項目](column-row-settings/manual-vs-dynamic-rows.md)」。


## 常見問答

| 問題 | 回答 |
|---|---|
| 灰色欄的百分比以哪些「*總計*」為依據？ | 這項「*總計*」取決於「**[!UICONTROL 列設定]**」中的「**[!UICONTROL 百分比]**」設定選取項目：<ul><li>依欄計算百分比 - 此為預設設定。百分比是以「表格總計」為依據。</li><li>依列計算百分比 - 百分比是以「總量」為依據。</li></ul> |
| **[!UICONTROL 「包含未指定 (無)」]**&#x200B;設定對總計會有何影響？ | 如果取消勾選「包含未指定（無）」設定，「無/未指定」列將從表格和「表格總計」中遭到移除，且這種情形會持續在任何使用[「總計」量度型別](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)的計算量度中生效。 |
| 如果在自由表格套用自訂表格篩選器，篩選器是否會採計我的所有計算量度和條件式格式？ | 目前不會。**[!UICONTROL 包含Ubnspecified (None)]**&#x200B;已考慮在內，但自訂資料表篩選器不會影響下列專案：<ul><li>條件式格式使用的欄最大值 / 最小值範圍會檢查所有資料。</li><li>使用「**[!UICONTROL 總量]**」量度類型的計算量度 。</li><li>內含的函數可計算自由表格中所有列的計算量度：「欄加總」、「欄最大值」、「欄最小值」、「計數」、「平均值」、「中位數」、「百分位數」、「四分位數」、「列計數」、「標準差」、「變數」、「累積」、「累積平均值」、「迴歸變數」、「T 分數」、「T 檢定」、「Z 分數」和「Z 檢定」。</li></ul> |
| 在計算量度中，**[!UICONTROL 「總量」]**&#x200B;量度類型會反映什麼？ | 「**[!UICONTROL 總量]**」只會持續參考「**[!UICONTROL 總量]**」，不會反映套用至表格或「**[!UICONTROL 表格總計]**」的篩選器。 |
| 如果資料經由自由表格複製貼上或透過 CSV 下載，系統會顯示哪項總計？ | 總列數只會反映「**[!UICONTROL 表格總計]**，並遵從欄的「**[!UICONTROL 顯示總計]**」設定。 |

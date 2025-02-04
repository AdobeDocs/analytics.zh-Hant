---
description: Analysis Workspace 總計的計算方式。
title: Analysis Workspace 總計
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 17%

---

# 工作區總計

在自由表格中，每個劃分層級都會顯示總列數，當中會顯示兩個總計數字：

![自由格式表格強調顯示總計與表格總計。](assets/total-row.png)

* **[!UICONTROL 資料表總計]** ➊ — 此總計通常等於[!UICONTROL 總計]或為其中一部分。 總計反映了自由表格內套用的任何表格篩選器，包括[!UICONTROL 不包含任何專案]選項。
* **[!UICONTROL 總計]** (**[!UICONTROL 個，共]**&#x200B;個&#x200B;*數字*➋) — 此總計代表已收集的所有事件。 當篩選器套用至面板層級或自由表格時，此總計會經過調整，以反映符合篩選條件的所有事件。




## 顯示總計

在![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 欄設定]**&#x200B;下，有&#x200B;**[!UICONTROL 顯示總計]**&#x200B;和&#x200B;**[!UICONTROL 顯示總計]**&#x200B;的選項。 如果未勾選這些設定，總計會從表格中移除；若總計沒有意義，就可能需要移除表格。


[靜態列](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)總計的行為方式不同，且使用![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 列設定]**&#x200B;控制。

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 將目前資料列的總和顯示為總計]** | 顯示表格中的使用者端列數總和。 此總計&#x200B;**不會**&#x200B;刪除重複量度，例如工作階段或人員。 |
| **[!UICONTROL 顯示總計]** | 顯示伺服器端總和。 此總計會去除重複量度，例如工作階段或人員。 |

檢視自由表格中的[動態與靜態維度專案](column-row-settings/manual-vs-dynamic-rows.md)。


## 常見問答

| 問題 | 回答 |
|---|---|
| 灰色資料行百分比以哪些&#x200B;*總計*&#x200B;為依據？ | 此&#x200B;*總計*&#x200B;取決於&#x200B;**[!UICONTROL 列設定]**&#x200B;下的&#x200B;**[!UICONTROL 百分比]**&#x200B;設定選取專案：<ul><li>依欄計算百分比 — 此為預設值。 百分比是以表格總計為基礎。</li><li>依列計算百分比 — 百分比以總計為基礎。</li></ul> |
| **[!UICONTROL 「包含未指定 (無)」]**&#x200B;設定對總計會有何影響？ | 如果取消勾選「包含未指定（無）」設定，「無/未指定」列將從表格和「表格總計」中遭到移除，且這種情形會持續在任何使用[「總計」量度型別](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md)的計算量度中生效。 |
| 如果在自由表格套用自訂表格篩選器，篩選器是否會採計我的所有計算量度和條件式格式？ | 目前不會。**[!UICONTROL 包含Ubnspecified (None)]**&#x200B;已考慮在內，但自訂資料表篩選器不會影響下列專案：<ul><li>條件式格式使用的欄最大值/最小值範圍會檢視所有資料。</li><li>使用&#x200B;**[!UICONTROL 總計]**&#x200B;個量度型別的計算量度。</li><li>使用函式計算自由表格中所有列的計算量度：欄總和、欄最大值、欄最小值、計數、平均值、中位數、百分位數、四分位數、列計數、標準差、變異數、累積、累積平均值、回歸變數、T分數、T檢定、Z分數和Z檢定。</li></ul> |
| 在計算量度中，**[!UICONTROL 總量]**&#x200B;量度型別會反映什麼？ | **[!UICONTROL 總計]**&#x200B;繼續參考&#x200B;**[!UICONTROL 總計]**，並未反映套用至資料表或&#x200B;**[!UICONTROL 資料表總計]**&#x200B;的篩選器。 |
| 如果資料經由自由表格複製貼上或透過 CSV 下載，系統會顯示哪項總計？ | 總列數僅反映&#x200B;**[!UICONTROL 資料表總計]**，並遵從資料行&#x200B;**[!UICONTROL 顯示總計]**&#x200B;設定。 |

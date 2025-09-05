---
title: 計算量度總計
description: 瞭解Analysis Workspace中的計算量度總計
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 94%

---

# 計算量度總計

在 Analysis Workspace 中檢視資料時，大多數情況下都會顯示計算量度總計。某些情況下無法提供總計，像是報表的列為混合格式時 (例如小數和貨幣混合)。

顯示總計時，通常會在伺服器端計算，這表示總計會去除重複的量度，例如造訪或訪客。在特定情況下，計算量度是透過表格各列的總和來於用戶端產生，這表示總計不會去除重複的量度，例如造訪或訪客。以下情境中會發生此情況：

* 當自由表格中使用[靜態列](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)，且選取&#x200B;**[!UICONTROL 顯示為目前列的總和]**&#x200B;選項 (預設值) 時。
* 在[環形圖視覺效果](/help/analyze/analysis-workspace/visualizations/donut.md)中，因此數字加起來為 100%。

若要了解 Analysis Workspace 中的總計，請瀏覽 [Workspace 總計](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total)。

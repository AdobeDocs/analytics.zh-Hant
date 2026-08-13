---
title: 計算量度總計
description: 瞭解Analysis Workspace中的計算量度總計
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
TQID: https://experienceleague.adobe.com/3UJF1Hl3nLqjYAiQuvcE4Jpq26MaTgeba5BmnVfvEps
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: dcae653e-62c6-4cc8-84e6-ee110b848296id: e318d41c-1d01-4c1e-9b18-1f61d435ceeeid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 94%

---

# 計算量度總計

在 Analysis Workspace 中檢視資料時，大多數情況下都會顯示計算量度總計。 某些情況下無法提供總計，像是報表的列為混合格式時 (例如小數和貨幣混合)。

顯示總計時，通常會在伺服器端計算，這表示總計會去除重複的量度，例如造訪或訪客。 在特定情況下，計算量度是透過表格各列的總和來於用戶端產生，這表示總計不會去除重複的量度，例如造訪或訪客。 以下情境中會發生此情況：

* 當自由格式表格中使用[靜態列](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)，且選取&#x200B;**[!UICONTROL 顯示為目前列的總和]**&#x200B;選項 (預設值) 時。
* 在[環形圖視覺效果](/help/analyze/analysis-workspace/visualizations/donut.md)中，因此數字加起來為 100%。

若要了解 Analysis Workspace 中的總計，請瀏覽 [Workspace 總計](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total)。

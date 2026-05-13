---
description: 取得 Analysis Workspace 常見問題的答案。
title: 常見問題集
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c069c44e-5426-4c1a-accc-8028662f2fdeid: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 598
ht-degree: 90%

---

# 常見問題集

+++使用 Analysis Workspace 的先決條件為何？
[透過 Adobe Analytics 擴充功能將資料傳送至 Adobe Analytics](/help/implement/launch/validate-publish-prod.md)：使用 Analysis Workspace 需要運作中實作。 請確認貴組織有將資料傳送至 Adobe，再開始使用此工具。 其他實作方式 (例如舊版手動實作) 也可有效運用。
+++

+++Analysis Workspace 的管理和存取需求為何？
請參閱[管理需求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。
+++

+++使用 Analysis Workspace 是否會影響資料收集？
Analysis Workspace 是報表工具，對於資料收集沒有影響。 任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。 您可以將不同的維度與量度組合拖曳到 Workspace 專案中，了解哪一種組合適合自己。 如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。 您也可以按一下左上方選單中的&#x200B;**[!UICONTROL 「專案]** > **[!UICONTROL 新專案」]**，以空白顯示窗開始操作。
+++

+++Analysis Workspace 專案中可以顯示多少報表套裝？
現在，您可以在 Analysis Workspace 中以更豐富的[多個報表套裝](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md)資料建立專案。
+++

+++如何實作 Analysis Workspace？
不需要特別實作。 所有具有Analytics Standard或Premium的公司都可使用Analysis Workspace。 但是將套用內容的標準權限 (例如報表套裝和專案元件)，以及適用於組織和共用專案。 請參閱[管理和存取需求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。
+++

+++可以將 Analysis Workspace 用於 Data Warehouse 嗎？
不建議將Analysis Workspace用於大量資料匯出。 它是視覺效果 Workspace，用於建立類似控制面板的分析專案。
+++

+++如何最佳化 Analysis Workspace 的效能？

請參閱[效能最佳化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)。

+++

+++資料如何進入您的 Analysis Workspace 專案？

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [資料進入 Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"} 的示範影片。

+++

+++如何追蹤 Workspace 的使用情況？

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [記錄追蹤](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"}的示範影片。

+++

+++我將量度拖曳至專案後，系統顯示「資料無效」。 如何解決此問題？

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。 舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。 因此，請改為並排放置量度。

+++

+++我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。 如何疑難排解此問題？

如果您成功建立了 Workspace 報表，但當中沒有任何資料，建議您檢查以下幾個事項：

* 仔細檢查報表套裝，確認報表中已填入資料。
* 如果您在報表中套用了區段，則可能是區段標準與任何資料皆不符。 請嘗試移除區段或調整區段定義。
* 檢查右上角的日期範圍，確認已設為您預期的值。
* 導覽至您的網站，使用[除錯工具](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)驗證資料正在收集中。


+++

+++作為唯讀使用者，我可以在 Analysis Workspace 中執行哪些動作？
專案以唯讀方式共用時，所有編輯功能和特色皆完全停用，且收件者僅可變更下拉式選單，以預先定義的方式將篩選器套用至面板。
+++

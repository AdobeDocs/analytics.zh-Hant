---
description: 工作區常見問答集
title: 常見問題集和疑難排解工作區
feature: Workspace 基本知識
role: 業務從業人員, 管理員
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 100%

---


# 常見問題集

| 問題 | 回答 |
|--- |--- |
| 使用 Analysis Workspace 的必要條件為何？ | [透過 Adobe Experience Platform Launch 將資料傳送至 Adobe Analytics](/help/implement/launch/validate-publish-prod.md)：使用 Analysis Workspace 需要先有效實施工具。請確認您的組織確實將資料傳送至 Adobe，再開始使用工具。其他實施方式 (例如 DTM 和舊版的手動實施) 也可有效運用。 |
| Analysis Workspace 的管理和存取需求為何？ | 請參閱[管理需求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 使用 Analysis Workspace 是否會影響資料收集？ | Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到工作區專案中，了解哪一種組合適合自己。如果您意外將無效的元件拖曳到工作區專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。您也可以按一下左上方功能表中的&#x200B;*[!UICONTROL 「專案] > [!UICONTROL 新專案」]*，以空白顯示窗開始操作。 |
| Analysis Workspace 專案中可以顯示多少報表套裝？ | 現在，您可以在 Analysis Workspace 中以更豐富的[多個報表套裝](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html)資料建立專案。 |
| 如何實施 Analysis Workspace？ | 不需要特別實施。所有已安裝 Analytics Standard 或 Premium 的公司都能使用 Analysis Workspace。但是將套用內容的標準權限 (例如報表套裝和專案元件)，以及適用於組織和共用專案。請參閱[管理和存取需求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| Analysis Workspace 會改變 Adobe Analytics 中預先設定的報表嗎？ | 不會。因為這是單獨的環境，所以不會改變 Adobe Analytics 中您現有或預先設定的報表。您仍可應用採用 Analysis Workspace 的標準「Reports &amp; Analytics」和「Report Builder」報表。 |
| 可以將 Analysis Workspace 用於 Data Warehouse 嗎？ | 不建議將 Analysis Workspace 用於大量資料匯出。它是視覺效果工作區，用於建立類似控制面板的分析專案。 |
| 如何最佳化 Analysis Workspace 的效能？ | 請參閱[效能最佳化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)。 |

## 疑難排解

**我將量度拖曳到專案後，系統顯示「資料無效」。**

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。因此，請改為並排放置量度。

**我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。**

如果您成功建立了工作區報表，但當中沒有任何資料，建議您檢查以下幾個事項：

* 仔細檢查報表套裝，確認報表中已填入資料。
* 如果您在報表中套用了區段，則可能是區段標準與任何資料皆不符。請嘗試移除區段或調整區段定義。
* 檢查右上角的日期範圍，確認已設為您預期的值。
* 導覽至您的網站，使用[除錯工具](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html)驗證資料正在收集中。
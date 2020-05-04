---
description: 工作區常見問答集
title: 常見問題與疑難排解工作區
translation-type: tm+mt
source-git-commit: 7fbeac0488fbe9b3d10d7c1242f31250f1c7dc16

---


# 常見問題集

| 問題 | 回答 |
|--- |--- |
| 使用分析工作區的先決條件為何？ | [透過 Adobe Experience Platform Launch 將資料傳送至 Adobe Analytics](/help/implement/launch/validate-publish-prod.md)：使用 Analysis Workspace 需要先有效實施工具。請確認您的組織確實將資料傳送至 Adobe，再開始使用工具。其他實施方式 (例如 DTM 和舊版的手動實施) 也可有效運用。 |
| Analysis Workspace 的管理和存取需求為何？ | 請參閱 [管理需求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 使用分析工作區是否會影響資料收集？ | Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到 Workspace 專案中，了解哪一種組合適合自己。如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。You can also start with a clean slate by clicking *[!UICONTROL Project]>[!UICONTROL New]*in the upper left menu. |
| Analysis Workspace 專案中可以顯示多少報表套裝？ | You can now create projects in Analysis Workspace with data from more [multiple report suites](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html). |
| 如何實施 Analysis Workspace？ | 不需要特別實施。所有已安裝 Analytics Standard 或 Premium 的公司都能使用 Analysis Workspace。但是將套用內容的標準權限 (例如報表套裝和專案元件)，以及適用於組織和共用專案。請參閱[管理和存取需求](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| Analysis Workspace 會改變 Adobe Analytics 中預先設定的報表嗎？ | 不會。因為這是單獨的環境，所以不會改變 Adobe Analytics 中您現有或預先設定的報表。您仍可應用採用 Analysis Workspace 的標準「Reports &amp; Analytics」和「Report Builder」報表。 |
| 可以將 Analysis Workspace 用於 Data Warehouse 嗎？ | 不建議將 Analysis Workspace 用於大量資料匯出。它是視覺效果工作區，用於建立類似控制面板的分析專案。 |
| 如何最佳化 Analysis Workspace 的效能？ | 請參閱[效能最佳化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)。 |
| Analysis Workspace 的功能與 Ad Hoc Analysis 相比如何？ | See [Analysis Workspace compared to Ad Hoc Analysis](/help/analyze/analysis-workspace/workspace-faq/adhocanalysis-vs-analysisworkspace.md). |

## 疑難排解

**我將量度拖曳到專案後，系統顯示「資料無效」。**

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。請改為並排放置量度。

**我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。**

如果您成功建立工作區報表，但沒有資料，您可以檢查以下幾項：

* 再次檢查報表套裝，並確認其已填入資料。
* 如果您在報表中套用區段，區段標準可能不符合任何資料。 請嘗試移除區段或調整區段定義。
* 檢查右上角的日期範圍，並確定它已設為您預期的值。
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.
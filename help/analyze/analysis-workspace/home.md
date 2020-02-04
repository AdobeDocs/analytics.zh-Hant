---
description: 如何開始使用 Adobe Analytics。
keywords: Analysis Workspace
title: 快速入門指南
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Analysis Workspace

Analysis Workspace 是 Adobe 的旗艦級工具之一，可供組織運用資料進行可實際執行的決策。自由表格這項最常用的視覺效果，可讓您運用維度、量度、區段和日期範圍輕鬆建立自訂報表。

## 必備條件

[透過 Adobe Experience Platform Launch 將資料傳送至 Adobe Analytics](/help/implement/launch/validate-publish-prod.md): 使用 Analysis Workspace 需要先有效實施工具。請確認您的組織確實將資料傳送至 Adobe，再開始使用工具。其他實施方式 (例如 DTM 和舊版的手動實施) 也可有效運用。

## 在 Workspace 中提取基本排名報表

運用 Analysis Workspace 提取基本排名報表。排名報表會顯示每個維度值的匯總完整數據檢視，從最大的數值開始依序顯示。這類報表類型有助於查看您網站的哪些元件成效最佳，例如哪些頁面獲得最多流量或哪些產品銷售最多。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
3. 在上方的導覽列按一下「Workspace」。
4. 按一下「建立新專案」按鈕。
5. 在模組快顯視窗中，確認已選取「空白專案」，然後按一下「建立」。
6. 左側應會顯示含有維度、量度、區段和日期範圍的清單。找到「頁面」維度 (顯示為橙色)，將該維度拖曳至畫布上顯示「將維度放置在此處」的位置。
7. 請注意，如果報表套裝中含有資料，您就會看到顯示當月成效最佳頁面的報表。Analysis Workspace 會自動在報表中填入[「發生次數」](/help/components/c-variables/c-metrics/metrics-occurrences.md)量度。
8. 找出「造訪次數」量度 (顯示為綠色)，並將此量度拖曳到「發生次數」量度標題&#x200B;**中**&#x200B;或&#x200B;**旁邊** (請避免放到量度上方)。如果將「造訪次數」量度拖曳到「發生次數」上，前者就會在報表中取代後者。如果將「造訪次數」量度拖曳到「發生次數」旁，兩個量度會並排顯示。
9. 如果您想要儲存專案，請按一下左上方功能表中的&#x200B;*[!UICONTROL 「專案]>[!UICONTROL 儲存」]*。

## 在 Workspace 中提取基本趨勢報告

運用 Analysis Workspace 提取基本趨勢報告。趨勢報告會依據所選日期範圍顯示一段時間以來的量度檢視。這類報表有助於識別一段期間內的趨勢，且可用於評估業務決策的成功與否。舉例來說，您可以檢視一段期間內的頁面檢視趨勢報告，評估網站的重新設計是否造成流量的增減。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
3. 在上方的導覽列按一下「Workspace」。
4. 按一下「建立新專案」按鈕。
5. 在模組快顯視窗中，確認已選取「空白專案」，然後按一下「建立」。
6. 左側應會顯示含有維度、量度、區段和日期範圍的清單。找到「頁面檢視」維度，並將該維度拖曳至畫布上標為「將量度放置在此處」的小空間。請避免放置在維度專用的空間 (至少在本次練習中不要這麼做)。
7. 請注意，如果報表套裝中含有資料，您應該會看到目前月份的基本頁面檢視趨勢報告。Analysis Workspace 會自動加入「天」日期範圍，以便您查看當月的頁面檢視趨勢。
8. 在左側日期範圍元件清單中找到「週」日期範圍 (顯示為紫色)。按一下日期範圍標題以展開並查看所有日期範圍元件，或使用搜尋列搜尋元件。
9. 將「週」日期範圍拖曳至畫布上的「天」日期範圍標題上方，藉此取代「天」。
10. 請注意，此時趨勢報告會按週彙總資料，而非按天。
11. 如果您想要儲存專案，請按一下左上方功能表中的&#x200B;*[!UICONTROL 「專案]>[!UICONTROL 儲存」]*。

## 透過工具進行實驗

Analysis Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到 Workspace 專案中，瞭解哪一種組合適合自己。

如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。您也可以按一下左上方功能表中的&#x200B;*[!UICONTROL 「專案]>[!UICONTROL 新專案」]*，以空白顯示窗開始操作。

## 疑難排解

**我將量度拖曳到專案後，系統顯示「資料無效」。**

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。因此，請改為並排放置量度。

**我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。**

如果您成功建立了工作區報表，但當中沒有任何資料，建議您檢查以下幾個事項:

* 再次檢查報表套裝，確認報表中已填入資料。
* 如果報表中有使用區段，可能是區段標準與任何資料皆不符。請嘗試移除區段或調整區段定義。
* 檢查右上方的日期範圍，確認已設為您需要的值。
* 導覽至您的網站，使用除錯程式來驗證系統確實開始收集所需資料。

## 其他資源

* [Analysis Workspace 發行說明](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md): 詳閱工具採用的最新功能。
* [在 YouTube 觀看 Analysis Workspace 教學](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): 瞭解如何透過這項廣泛播放清單使用 Analysis Workspace 的多數功能。
* 產品使用秘訣: Analysis Workspace 右下方有時候會顯示每日秘訣，並搭配短片。如果您關閉了這些秘訣，仍可以隨時前往&#x200B;*[!UICONTROL 「說明]>[!UICONTROL 秘訣」]*查看。
* [Analysis Workspace 社群](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): 與其他使用者討論 Analysis Workspace 相關事項，並可投票選出想要加到工具中的功能。
* 部落格貼文:
   * [使用更聰明的分析強化組織](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [全新的 Adobe Analytics 功能讓您更容易取得最強大的前瞻分析](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [使用 Analysis Workspace 充分發揮生產力的 5 個祕訣](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Analysis Workspace 的更快速見解](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [為何應使用 Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 下一步

如要加深對 Analysis Workspace 的理解，您有許多方向可走。以下是 Adobe 建議的幾個基本方向:

### 如果您是想要擴充 Analysis Workspace 使用方式相關知識的使用者

* [Workspace UI 的詳細資料](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): 既然您已建立基本報表，接下來請進一步熟悉介面的其餘部分。
* [Workspace 的視覺效果](visualizations/freeform-analysis-visualizations.md): 自由表格僅僅是 Analysis Workspace 資料視覺效果的其中一種類型。請進一步瞭解如何使用其他視覺效果，例如折線圖、長條圖和地理分佈圖。
* [Workspace 的維度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): 進一步瞭解各項維度，以及如何在排名報表之外使用這些維度。
* [Workspace 的量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md): 進一步瞭解各項量度，以及如何在自由表格的其他部分使用這些量度。
* [區段簡介](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): 瞭解各項區段，並使用區段提取基本報表。
* [Workspace 的日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): 瞭解相對日期和滾動日期，並在 Workspace 專案中使用這些設定。
* 共用 Workspace 中的專案: 向同事展示您建立的出色 Workspace 專案。
* [(進階) Workspace 的面板](c-panels/panels.md): 使用 Workspace 的進階功能，例如「歸因」和「區段比較」。

### 如果您是想要改善組織工作區品質的分析師和管理員

* [Analysis Workspace 權限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html): 透過 Adobe Admin Console 在 Workspace 中指派使用者權限。
* [建立解決方案設計文件](/help/implement/prepare/solution-design.md): 開始為組織規劃收集其他網站專用維度或量度的方式。
* [Workspace 中的範本](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): 建立範本，方便讓同事根據自己的需求量身打造專案空間。
* [Workspace 組織](curate-share/curate.md): 建立一項可用元件有限的專案，讓不熟悉工具的人更容易存取工作區。

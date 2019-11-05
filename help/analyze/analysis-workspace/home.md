---
description: 如何開始使用Adobe Analytics。
keywords: Analysis Workspace
seo-description: 如何開始使用Adobe Analytics。
seo-title: 快速入門手冊
solution: Analytics
title: 快速入門手冊
topic: Reports and Analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analysis Workspace

分析工作區是Adobe的旗艦工具之一，可協助您組織做出可操作的資料決策。 最常見的視覺化形式表格，可讓您使用維度、量度、區段和日期範圍輕鬆建立自訂報表。

## 必備條件

[使用Adobe Experience Platform Launch將資料傳送至Adobe Analytics](/help/implement/implement-with-launch/validate-publish-prod.md):使用分析工作區需要有效的實施。 請確定您的組織在使用該工具之前已傳送資料至Adobe。 其他實作（例如DTM或舊版手動實作）也可以運作。

## 在工作區中提取基本排名報表

使用分析工作區提取基本排名報表。 排名報表會顯示每個維度值的匯總總檢視，首先顯示最大值。 這些報表類型有助於查看您網站的哪些元件最有效，例如哪些頁面獲得最多流量或哪些產品銷售最多。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
3. 在頂端導覽列中，按一下「工作區」。
4. 按一下「建立新專案」按鈕。
5. 在模式快顯視窗中，請確定已選取「空白專案」，然後按一下「建立」。
6. 在左側，您應該會看到維度、量度、區段和日期範圍的清單。 找到「頁面」維度（彩色橙色），並拖曳至畫布上顯示「拖曳維度到此處」的位置。
7. 請注意，如果報表套裝有資料，則可看到顯示本月最上層頁面的報表。 分析工作區會自動填入具有「發生次 [數](/help/components/c-variables/c-metrics/metrics-occurrences.md) 」度量的報表。
8. 找出「瀏覽」量度（彩色綠色），並將其拖曳 **到** 「發 **** 生次數」量度標題旁（請避免將其置於量度上方）。 如果您將「瀏覽」度量拖曳至「發生次數」之上，則會在報表中取代該度量。 如果您將「瀏覽」度量拖曳至「發生次數」旁，兩個度量會並排顯示。
9. 如果您想要儲存專案，請按一下左上 *[!UICONTROL 方功能表中的「]專案[!UICONTROL &gt;]* 儲存」。

## 在工作區中提取基本趨勢報表

使用分析工作區提取基本趨勢報表。 趨勢報表顯示使用所選日期範圍之量度的時相檢視。 這些類型的報表有助於識別一段時間的趨勢，並可用於評估業務決策的成功或失敗。 例如，您可以檢視一段時間趨勢化的頁面檢視報表，查看網站重新設計是否有助於增加或減少流量。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
3. 在頂端導覽列中，按一下「工作區」。
4. 按一下「建立新專案」按鈕。
5. 在模式快顯視窗中，請確定已選取「空白專案」，然後按一下「建立」。
6. 在左側，您應該會看到維度、量度、區段和日期範圍的清單。 找到「頁面檢視」維度，並將其拖曳至畫布上標有「拖曳量度到此處」的小空間。 請避免將它拖曳至為尺寸保留的空間（至少在本練習中）。
7. 請注意，如果報表套裝有資料，您應該會看到目前月份趨勢的基本頁面檢視報表。 分析工作區會自動進入「日」日期範圍，以便您查看當月的頁面檢視趨勢。
8. 在左側日期範圍元件清單中找出「周」日期範圍（彩色紫色）。 按一下日期範圍標題以展開並查看所有日期範圍元件，或使用搜尋列。
9. 將週日期範圍拖曳至畫布上的日日期範圍標題上方，以取代它。
10. 請注意，您的趨勢報表現在會依周而非日匯總。
11. 如果您想要儲存專案，請按一下左上 *[!UICONTROL 方功能表中的「]專案[!UICONTROL &gt;]* 儲存」。

## 使用工具進行實驗

由於分析工作區是報告工具，因此對資料收集沒有影響。 不加區分地將元件拖曳至專案中，以檢視哪些功能有效，不會造成任何影響。 將不同的維度和量度組合拖曳至您的工作區專案，以檢視哪些項目可供您使用。

如果您意外將無效的元件拖曳至您的工作區專案，或想要返回步驟，請按ctrl+Z(Windows)或cmd+Z(Mac)，以復原最後執行的動作。 您也可以按一下左上方功能表中的「專 *[!UICONTROL 案]&gt;新[!UICONTROL 增]* 」(Project &gt; New)，從乾淨的石板開始。

## 疑難排解

**當我拖曳量度時，會顯示「無效資料」。**

無效的資料表示Adobe無法使用報表中使用的維度和度量組合來傳回資料。 例如，兩個彼此堆疊在一起的量度無法傳回為資料，因為無法以這種方式顯示兩個量度。 請改為並排放置量度。

**當我拖曳量度時，我看不到任何實際資料——只有零。**

如果您成功建立工作區報表，但沒有資料，您可以檢查以下幾項：

* 請再檢查一次報表套裝，並確定它已填入資料。
* 如果您在報表中使用區段，區段標準可能不符合任何資料。 嘗試移除區段或調整區段定義。
* 檢查右上方的日期範圍，並確定它已設為您預期的值。
* 導覽至您的網站，然後使用除錯程式來驗證所收集的資料。

## 其他資源

* [分析工作區發行說明](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md):閱讀工具中引入的最新功能。
* [YouTube上的分析工作區](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS):透過此廣泛的播放清單，瞭解如何使用分析工作區中的大部分功能。
* 產品內提示：當天的秘訣，以及短片，偶爾會出現在分析工作區的右下角。 如果這些秘訣被關閉，您隨時都可以透過「說 *[!UICONTROL 明]&gt;秘訣[!UICONTROL (Tips]* )」取得。
* [分析工作區社群](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace):與其他使用者討論分析工作區，並就您想在工具中檢視的功能進行投票。
* 部落格文章：
   * [使用更聰明的分析強化組織](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [全新的Adobe Analytics功能讓您更容易獲得強大的見解](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [使用分析工作區將生產力提升到最大的5個秘訣](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [使用分析工作區更快速地洞察](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [為何應使用 Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 下一步

要加深您對「分析工作區」的瞭解，有許多方向要走。 以下是Adobe建議的一些基本概念：

### 針對想要擴充分析工作區使用知識的使用者

* [工作區UI的詳細資訊](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md):現在您已建立基本報表，請更熟悉其他介面。
* [工作區中的視覺化](visualizations/freeform-analysis-visualizations.md):自由表格只是分析工作區中的一種視覺化類型。 瞭解如何使用其他視覺化，例如折線圖、長條圖和地理地圖。
* [工作區中的維度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md):進一步瞭解哪些維度以及如何在排名報表中使用這些維度。
* [工作區中的度量](/help/analyze/analysis-workspace/components/apply-create-metrics.md):進一步瞭解什麼是量度，以及如何在自由表格的其他部分使用量度。
* [區段簡介](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md):瞭解什麼是區段，並使用區段提取基本報表。
* [工作區中的日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md):瞭解相對和遞延日期，並在工作區專案中使用這些日期。
* 在工作區中共用專案：向同事顯示您建立的絕佳工作區專案。
* [（進階）工作區中的面板](c-panels/panels.md):使用工作區中的進階功能，例如歸因和區段比較。

### 針對想要改善其組織中工作環境品質的分析師和管理員

* [分析工作區權限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html):透過Adobe Admin Console將使用者權限指派至工作區。
* [建立解決方案設計檔案](/help/implement/prepare/solution-design.md):開始規劃您的組織如何收集您網站的特定其他維度或度量。
* [工作區中的範本](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md):建立範本，讓同事可以根據自己的需求量身打造專案空間。
* [工作區組織](curate-share/curate.md):建立專案以限制可用元件，讓不熟悉此工具的人更容易存取工作區

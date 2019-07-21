---
description: 如何開始使用Adobe Analytics。
keywords: Analysis Workspace
seo-description: 如何開始使用Adobe Analytics。
seo-title: 快速入門手冊
solution: Analytics
title: 快速入門手冊
topic: Reports & Analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: a0158b98089c044091f61796d782604865aa4eba

---


# Analysis Workspace

Analysis Workspace是Adobe旗艦工具之一，可為您的組織做出可行的資料決策。最常見的視覺效果是自由表格，可讓您使用維度、度量、區段和日期範圍輕鬆建立自訂報表。

## 必備條件

[使用Adobe Experience Platform Launch將資料傳送至Adobe Analytics](../../implement/implement-with-launch/validate-publish-prod.md)：使用分析工作區需要工作實作。請務必在使用工具之前，先將資料傳送至Adobe。其他實作(例如DTM或舊版手動實作)也可以運作。

## 在工作區中提取基本排名報表

使用分析工作區提取基本排名報表。排名報表會顯示每個維度值的匯總檢視，首先顯示最大值。這些類型的報表有助於查看您網站的哪些元件最有效，例如哪些頁面得到最大流量或哪些產品銷售最多。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. 按一下右上方的方形圖示，然後按一下彩色的Analytics標誌。
3. 在頂端導覽列中，按一下「工作區」。
4. 按一下「建立新專案」按鈕。
5. 在模型彈出式視窗中，確定已選取「Blank Project」(空白專案)，然後按一下「Create」(建立)。
6. 在左側，您應該看到維度、度量、區段和日期範圍的清單。找出「頁面」維度(彩色橘色)，並將它拖曳至畫布上指出「拖曳維度至此」的畫布。
7. 請注意，如果報表套裝具有資料，則會顯示一個報表，顯示本月的排名最前的頁面。Analysis Workspace automatically populated the report with the [Occurrences](../../components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). 如果您將「瀏覽次數」度量拖曳至「發生次數」，則會在報表中取代度量。如果您拖曳「發生次數」旁邊的「瀏覽次數」度量，兩個度量都會並排顯示。
9. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## 在工作區中提取基本趨勢報表

使用分析工作區提取基本趨勢報表。趨勢報表會使用所選日期範圍顯示度量的時相檢視。這些類型的報表有助於識別隨時間變化的趨勢，並可用來評估業務決策的成敗。例如，您可以查看某個頁面檢視報表隨時間趨勢的趨勢，瞭解網站重新設計是否有助於增加或減少流量。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. 按一下右上方的方形圖示，然後按一下彩色的Analytics標誌。
3. 在頂端導覽列中，按一下「工作區」。
4. 按一下「建立新專案」按鈕。
5. 在模型彈出式視窗中，確定已選取「Blank Project」(空白專案)，然後按一下「Create」(建立)。
6. 在左側，您應該看到維度、度量、區段和日期範圍的清單。找到「頁面檢視」維度，並將它拖曳至畫布上標示為「拖曳量度至此」的小型空間。避免將它放置在保留維度的空間中(至少用於本練習)。
7. 請注意，如果報表套裝具有資料，您應該會看到當月的基本頁面檢視報表趨勢。分析工作區會自動引入「日」日期範圍，讓您查看當月的頁面檢視趨勢。
8. 在左側的日期範圍元件清單中找出「周」日期範圍(彩色的紫色)。按一下日期範圍標題以展開並查看所有日期範圍元件，或使用搜尋列。
9. 將「周」日期範圍拖曳至畫布上的日期範圍標題上方，以取代它。
10. 請注意，您的趨勢報表現在是依周匯總，而非日匯總。
11. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## 實驗工具

由於Analysis Workspace是報告工具，因此不會影響資料收集。不需重新計算，將元件拖曳至專案中，即可查看哪些項目有效。將維度和度量的不同組合拖曳至工作區專案，以瞭解您可以使用甚麼。

如果您意外拖曳無效的元件至工作區專案，或想要返回步驟，請按Ctrl+ Z(Windows)或cmd+ Z(Mac)來還原最後的動作。You can also start with a clean slate by clicking *[!UICONTROL Project]&gt;[!UICONTROL New]* in the upper left menu.

## 疑難排解

**當我拖曳量度時，表示「無效資料」。**

無效的資料表示Adobe無法使用報表中使用的維度和度量來傳回資料。例如，堆疊在彼此之上的兩個量度無法作為資料傳回，因為無法以這種方式顯示兩個量度。請改為並排放置量度。

**拖曳量度時，我不會看到任何實際資料-只有零。**

如果您成功建立工作環境報表，但沒有資料，則有一些項目可以檢查：

* 再次檢查報表套裝，確定報表套裝已填入資料。
* 如果您使用報表中的區段，區段標準可能不符合任何資料。嘗試移除區段或調整區段定義。
* 檢查右上方的日期範圍，確定其設定為您預期的值。
* 導覽至您的網站，並使用除錯程式驗證是否已收集資料。

## 其他資源

* [分析工作區發行說明](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md)：閱讀工具中介紹的最新功能。
* [YouTube的分析工作區](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)：透過這個廣泛的播放清單，瞭解如何使用分析工作區中的大部分功能。
* 產品內秘訣：每日秘訣以及短片，偶爾會出現在分析工作區的右下角。If these tips are dismissed, they can be reached through *[!UICONTROL Help]&gt;[!UICONTROL Tips]* at any time.
* [分析工作區社群](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)：與其他使用者討論分析工作區，並對您想要在工具中看到的功能進行投票。
* 部落格文章：
   * [使用更聰明的分析強化組織](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [全新Adobe Analytics功能讓深入見解更容易存取](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [使用分析工作區來提升生產力的秘訣](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [使用分析工作區加快前瞻分析](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [為何應使用 Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 下一步

為了加深對分析工作區的瞭解，有許多方向可循。以下是Adobe建議的一些基本概念：

### 針對想要進一步瞭解如何使用分析工作區的使用者

* [工作區UI的詳細資訊](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)：現在您已建立基本報表，更熟悉介面其餘部分。
* [工作區中的視覺化](visualizations/freeform-analysis-visualizations.md)：自由格式表格只是分析工作區中的一種視覺化類型。瞭解如何使用其他視覺效果，例如折線圖、橫條圖和地理地圖。
* [工作區中的維度](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)：進一步瞭解哪些維度以及如何在排名報表中使用這些維度。
* [工作區中的度量](../../analyze/analysis-workspace/components/apply-create-metrics.md)：進一步瞭解哪些量度以及如何在自由表格的其他部分使用它們。
* [區段簡介](../../analyze/analysis-workspace/components/t-freeform-project-segment.md)：瞭解使用區段的區段以及提取基本報表的方法。
* [工作區中的日期範圍](../../analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)：瞭解相對和滾動日期，並在工作區專案中使用它們。
* 在工作區中共用專案：向同事展示您所建立的絕佳工作區專案。
* [(進階)工作區中的面板](c-panels/panels.md)：使用工作區中的進階功能，例如屬性和區段比較。

### 為分析師和admin尋求改善組織中工作區品質的

* [分析工作區權限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)：透過Adobe Admin Console指派使用者權限至工作環境。
* [建立解決方案設計文件](../../implement/prepare/solution-design.md)：開始規劃組織如何收集您網站專用的其他維度或度量。
* [工作區中的範本](../../analyze/analysis-workspace/build-workspace-project/starter-projects.md)：建立範本，讓同事可以從專案空間開始，根據他們的需求進行創作。
* [工作區組織](curate-share/curate.md)：建立限制可用元件的專案，讓不熟悉工具的工作區更容易存取
---
description: '[!DNL Activity Map]中設定、設定和使用功能的常見問題。'
seo-description: '[!DNL Activity Map]中設定、設定和使用功能的常見問題。'
seo-title: '[!DNL Activity Map]常見問答集'
solution: Analytics
title: '[!DNL Activity Map]常見問答集'
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# [!DNL Activity Map] 常見問題解答

Frequently asked questions for setting up, configuring, and employing features in [!DNL Activity Map].

## 實作和 AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**問：啟用新功能的實作步驟為何[!DNL Activity Map]?**

答：請查看 [啟用[!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**問: 所有 Analytics 客戶都有權存取管理工具的「Activity Map 啟用」頁面嗎?**

A: Adobe SiteCatalyst customers do not have access to the Admin Console's [!DNL Activity Map] Enablement page. 只有簽訂 Adobe Analytics Standard 和 Adobe Analytics Premium 合約的公司有權存取此設定頁面。

**問: 新的 AppMeasurement 代碼可以透過「動態標籤管理」(DTM) 進行設定嗎?**

答: 是，您可以[手動實施](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html)新的 AppMeasurement 代碼。

**問: AppMeasurement v1.6 程式庫有什麼重大變更?**

A: The only change in AppMeasurement v1.6 is in the [!DNL Activity Map] link tracking process methodology that requires the collection of Page name, Link ID and RegionID.

**問: AppMeasurement 是否將在網域層級 (而非特定頁面) 推出?**

答: AppMeasurement 是在報表套裝層級推出。報表套裝層級通常與網域層級關聯，但這會依每次實作而有所不同。

**[!DNL Activity Map]問: DTM 會自動載入舊版 (1.3.4) Visitor API，而非 需要的版本 (1.5.1)。這會有問題嗎?**

答: 否。[!DNL Activity Map] 功能並不取決於VisitorAPI。

## [!DNL Activity Map] 應用程式 {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**[!DNL Activity Map]問: 我之前沒有在網站上使用 Visitor ClickMap，現在可以使用 嗎?**

答: 是否安裝舊版 (現在簡稱為 ClickMap) 並非實施新版本的先決條件。Adobe 還會在一段限定時間內繼續支援舊版。

**問：哪些瀏覽器和版本受支援[!DNL Activity Map]?**

答: 我們僅支援四種主要瀏覽器 (Chrome、Firefox、Safari 和 IE) 的最新版本。

**問: 預設覆蓋圖設定是什麼?**

A: By default, [!DNL Activity Map] shows ALL links that have collected data.

當客戶網頁頂端顯示彈出式面板時，位於彈出式面板下方之連結所屬的覆蓋圖，就會顯示在彈出式面板的頂端。

**問: 為什麼會遺失部分排名項目覆蓋圖?**

答: 有些排名連結會在頁面上隱藏 (例如子功能表連結)。因此也不會顯示其對應的連結覆蓋圖。因此您可以預期覆蓋圖排名會遺失部分特定的排名值，因為排名是針對頁面上的所有連結來進行計算 (顯示連結 + 隱藏連結)。

**問: 「全部連結」報表中的連結排名是如何決定的?**

* 在「**漸層**」和「**氣泡**」模式中: 「排名」是由量度欄決定。對於具有相同量度值的連結，再進一步根據連結 ID 的字母順序來排名。
* 而在「**獲益者和損失者**」模式中，排名主要是由「獲益 %」欄決定。對於具有相同獲益的連結，再進一步根據連結 ID 的字母順序來排名。

**[!DNL Activity Map]問: 為什麼 執行時，沒有收集連結點擊資料?**

A: While [!DNL Activity Map] is in use, link click data is not collected by the Analytics tag. 此行為符合 ClickMap 外掛程式的行為。

**問: 為什麼量度下拉式清單多次列出相同的量度?**

A: [!DNL Activity Map] lists metrics for all report suites. 因此，如果公司未執行[量度整合程序](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html)，可以預期會看到重複項目。

您可以利用量度下拉式清單，將計算量度清單限制為指派給已造訪頁面之報表套裝的量度。

**問：「所有連結[!DNL Activity Map]報表」與「報表與分析」報表的[!DNL Activity Map]比較？**

答：若要提取「所有連結報表」, [!DNL Activity Map]我們會建立劃分請求，如下所示：頁 [!DNL Activity Map] 面= "visitedpage"，依中的 [!DNL Activity Map] Link&amp;Region劃分 `<list of link&regions present in the page at rendering time>`。

To get an equivalent report in Reports &amp; Analytics, you would need to first navigate to the [!DNL Activity Map] Page report. There, you would filter for the visited pagename in [!DNL Activity Map]. The visited Pagename is shown in the left column in the [!DNL Activity Map] Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose [!DNL Activity Map] Links &amp; Regions as a secondary dimension.

不過，請務必注意，在「報告與分析」中取得的報表，會列出為該頁面收集的所有連結和地區。But [!DNL Activity Map] only reports on Links&amp;Regions that are currently present in the webpage. 所以，如果您擁有新聞網站，則只會顯示當下時間的新聞報導，而不會顯示當天稍早呈現的新聞報導。

**[!DNL Activity Map]問:  如何處理包含多個標記 (因此列出多個報表套裝) 的頁面?**

A: By default, [!DNL Activity Map] uses the report suite that is associated with the first tag that is sent by the page.

但您可透過「[!DNL Activity Map] 設定 &gt; 其他」索引標籤，選取其他已標記報表套裝。

**[!DNL Activity Map]問:  會掃描 Analytics 標記多久時間?**

答: 在頁面完成事件後，我們最多掃描 Analytics 標記 20 秒。

**問：如何處理[!DNL Activity Map]動態內容？**

A: [!DNL Activity Map] checks every 2 seconds to see if it has found changes in the state of the web page such as:

* HTML 內容變成可見
* HTML 內容變成隱藏
* 插入新的 HTML 內容

如果內容變成隱藏或顯示，應用程式會自動將受影響的連結狀態 (以及覆蓋圖) 從隱藏變更為顯示，或從顯示變更為隱藏。

如果插入新內容，應用程式會擷取關聯的連結、提取分析資料，並新增這些連結的覆蓋圖。

**問: 頁面流量報表是根據哪個量度?**

答: 所有顯示的資料都是根據頁面檢視。

**[!DNL Activity Map]問: 可否說明各種頁面類型的 行為?**

*網頁沒有 Analytics 標記*

會在工具列底下顯示警告訊息，指出沒有標記。

*網頁具有不相容 Analytics 標記 (AppMeasurement v1.5 或更舊版本)*

會顯示警告訊息，指出您需要(/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)將頁面程式碼升級至v1.6。

*[!DNL Activity Map]網頁具有相容的 Analytics 標記 (AppMeasurement v1.6 或更新版本)，但未在管理工具中啟用*

會顯示警告訊息，指出您需要要求您的管理員\[啟用 [!DNL Activity Map] 報表\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md")。

**問：我是否可[!DNL Activity Map]以透過[Analytics資料饋送匯出資料(contextData)](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)?**

答: 否。

## 區段 [!DNL Activity Map] : {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**問: 區段關聯至個別使用者區段嗎? Or are shared Admin-level segments available in[!DNL Activity Map]?**

A: [!DNL Activity Map] inherits your Admin-level segments (reporting segments) from Analytics.

**問: 區段可否用於即時模式?**

答: 否，區段不適用於即時模式。此功能等同於「Reports &amp; Analytics」中的即時報表。

## 虛擬報表套裝 {#section_BDB0CA9E732F478EAC349A79753A78DB}

**問：是否[!DNL Activity Map]與虛擬報表套裝相容？**

答: 是。However, due to virtual report suite limitations, [!DNL Activity Map]'s Live Mode is not compatible with virtual report suites.

---
description: 在Activity Map中設定、設定和使用功能的常見問題。
title: Activity Map 常見問題集
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 0e125be6e1710c65effa0adc8097e8916c8a3290

---


# Activity Map 常見問題集

在Activity Map中設定、設定和使用功能的常見問題。

## 實作和 AppMeasurement

**問：啟用新 Activity Map 的實作步驟為何？**

答：請檢閱[啟用 Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**問：所有 Analytics 客戶都有權存取管理工具的「Activity Map 啟用」頁面嗎？**

答：Adobe SiteCatalyst 客戶無權存取管理控制台的「Activity Map 啟用」頁面。只有Adobe Analytics Standard和Adobe Analytics Premium合約下的公司才能存取此設定頁面。

**問：新的 AppMeasurement 代碼可以透過「Dynamic Tag Management」(DTM) 進行設定嗎？**

答：是，您可以[手動實施](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html)新的 AppMeasurement 代碼。

**問：AppMeasurement v1.6 程式庫有什麼重大變更？**

答：AppMeasurement v1.6 的唯一變更是 Activity Map 連結追蹤處理方法，此方法需要收集頁面名稱、連結 ID 和地區 ID。

**問：AppMeasurement 是否將在網域層級 (而非特定頁面) 推出？**

答：AppMeasurement 是在報表套裝層級推出。報表套裝層級通常與網域層級關聯，但這與每個實作不同。

**問：DTM 會自動載入舊版 (1.3.4) Visitor API，而非 Activity Map 需要的版本 (1.5.1)。這會有問題嗎？**

答：不會。Activity Map功能並不取決於VisitorAPI。

## Activity Map 應用程式

<!--**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.-->

**問：Activity Map是否提供「檢視」資料？**

答：否，Adobe不會追蹤已檢視的連結。

**問：我之前沒有在網站上使用 Visitor ClickMap，現在可以使用 Activity Map 嗎？**

答：是否安裝舊版 (現在簡稱為 ClickMap) 並非實施新版本的先決條件。Adobe將在限定時間內繼續支援舊版。

**問：Activity Map 支援哪些瀏覽器和版本？**

答：我們支援4種主要瀏覽器（Chrome、Firefox、Safari和IE）的最新版本。

**問：預設覆蓋圖設定是什麼？**

答：依預設，Activity Map 會顯示有收集到資料的「所有」連結。

當快顯面板顯示在客戶網頁上方時，屬於位於快顯面板下方之連結的覆蓋圖可能會顯示在快顯面板上方。

**問：為什麼會遺失部分排名項目覆蓋圖？**

答：有些排名連結會在頁面上隱藏 (例如子功能表連結)。因此，不會顯示其對應的連結覆蓋。 因此，您可以預期會看到覆蓋圖排名遺漏某些特定排名值，因為排名會針對頁面中的所有連結（目前的連結+隱藏的連結）計算。

**問：「全部連結」報表中的連結排名是如何決定的？**

* 在&#x200B;**「漸層」**&#x200B;和&#x200B;**「氣泡」**&#x200B;模式中：「排名」是由量度欄決定。對於具有相同量度值的連結，排名會進一步根據連結ID的字母順序。
* 而在&#x200B;**「獲益者和損失者」**&#x200B;模式中，排名主要是由「獲益 %」欄決定。對於具有相同增益的連結，排名會進一步根據連結ID的字母順序。

**問：為什麼 Activity Map 執行時，沒有收集連結點擊資料？**

答：使用 Activity Map 時，Analytics 標記不會收集連結點擊資料。此行為會遵循ClickMap外掛程式的行為。

**問：「Activity Map 全部連結報表」與「Reports &amp; Analytics Activity Map」報表有何差異？**

答：若要提取 Activity Map 中的「全部連結報表」，我們會建立劃分請求，如下所示：Activity M ap 頁面 = &quot;visitedpage&quot;，依據`<list of link&regions present in the page at rendering time>`的 Activity Map 連結和地區來劃分。

若要在「報告與分析」中取得相等報表，您必須先導覽至「Activity Map頁面」報表。 您可在此篩選Activity Map中已瀏覽的頁面名稱。 已瀏覽的頁面名稱會顯示在Activity Map頁面詳細資料底部面板的左欄中。 找到頁面後，您可以從該頁面進行劃分，然後選擇「Activity Map連結與地區」作為次要維度。

不過，請務必注意，在R&amp;A中取得的報表會列出為該頁面收集的所有連結與地區。 但Activity Map僅會報告目前在網頁中出現的連結與地區。 所以如果有新聞網站，它只會顯示目前的新聞報導資料，而不會顯示當天早些時候的新聞報導。

**問：Activity Map 如何處理包含多個標記 (因此列出多個報表套裝) 的頁面？**

答：依預設，Activity Map 會使用頁面所傳送第一個標記相關聯的報表套裝。但您可透過「Activity Map 設定 > 其他」索引標籤，選取其他已標記報表套裝。

**問：Activity Map 會掃描 Analytics 標記多久時間？**

答：在頁面完成事件後，我們最多掃描 Analytics 標記 20 秒。

**問：Activity Map 如何處理動態內容？**

答：Activity Map 每 2 秒檢查一次，查看是否有如下所示的網頁狀態變更：

* 已顯示的HTML內容
* 隱藏的HTML內容
* 插入的新HTML內容

如果內容已隱藏或顯示，應用程式會自動將受影響的連結狀態（以及覆蓋圖）從隱藏變更為顯示，或從顯示變更為隱藏。

如果插入新內容，應用程式將擷取相關連結、擷取其分析資料，並新增這些連結的覆蓋圖。

**問：頁面流量報表是根據哪個量度？**

答：所有顯示的資料都是根據頁面檢視。

**問：可否說明各種頁面類型的 Activity Map 行為？**

*不含Analytics標籤的網頁*

工具列下方會顯示警告訊息，指出沒有標籤存在。

*網頁含有不相容的Analytics標籤（AppMeasurement v1.5或更舊版本）*

會顯示警告訊息，指出您需要將頁面程式碼升級至v1.6或更新版本。

*網頁具有相容的 Analytics 標記 (AppMeasurement v1.6 或更新版本)，但未在管理工具中啟用 Activity Map*

系統會顯示警告訊息，指出您需要請管理員\[啟用 Activity Map 報表。\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;)

**問：能否透過[Analytics 資料摘要](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)匯出 Activity Map 資料 (contextData)？**

答：否。

## Activity Map 中的分段

**問：區段關聯至個別使用者區段嗎？Are shared segments available in Activity Map?**

答：Activity Map會繼承Analytics的報表區段。

**問：區段可否用於即時模式？**

答：否，區段不適用於即時模式。此功能等同於「報告與分析」中的即時報告。

## 虛擬報表套裝

**問：Activity Map 是否與虛擬報表套裝相容？**

答：是。不過，由於虛擬報表套裝的限制，Activity Map的即時模式與虛擬報表套裝不相容。

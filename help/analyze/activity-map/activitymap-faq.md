---
description: 在 Activity Map 中安裝、設定和使用功能的常問的問題。
title: Activity Map 常見問題集
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Activity Map 常見問題集

在 Activity Map 中安裝、設定和使用功能的常問的問題。

## 實作和 AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**問: 啟用新 Activity Map 的實作步驟為何?**

答: 請檢閱[啟用 Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**問: 所有 Analytics 客戶都有權存取管理工具的「Activity Map 啟用」頁面嗎?**

答: Adobe SiteCatalyst 客戶無權存取管理控制台的「Activity Map 啟用」頁面。只有簽訂 Adobe Analytics Standard 和 Adobe Analytics Premium 合約的公司有權存取此設定頁面。

**問: 新的 AppMeasurement 代碼可以透過「動態標籤管理」(DTM) 進行設定嗎?**

答: 是，您可以[手動實施](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html)新的 AppMeasurement 代碼。

**問: AppMeasurement v1.6 程式庫有什麼重大變更?**

答: AppMeasurement v1.6 的唯一變更是 Activity Map 連結追蹤處理方法，此方法需要收集頁面名稱、連結 ID 和地區 ID。

**問: AppMeasurement 是否將在網域層級 (而非特定頁面) 推出?**

答: AppMeasurement 是在報表套裝層級推出。報表套裝層級通常與網域層級關聯，但這會依每次實作而有所不同。

**問: DTM 會自動載入舊版 (1.3.4) Visitor API，而非 Activity Map 需要的版本 (1.5.1)。這會有問題嗎?**

答: 否。Activity Map 功能不須依賴 VisitorAPI。

## Activity Map 應用程式 {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**問: 我之前沒有在網站上使用 Visitor ClickMap，現在可以使用 Activity Map 嗎?**

答: 是否安裝舊版 (現在簡稱為 ClickMap) 並非實施新版本的先決條件。Adobe 還會在一段限定時間內繼續支援舊版。

**問: Activity Map 支援哪些瀏覽器和版本?**

答: 我們僅支援四種主要瀏覽器 (Chrome、Firefox、Safari 和 IE) 的最新版本。

**問: 預設覆蓋圖設定是什麼?**

答: 依預設，Activity Map 會顯示有收集到資料的「所有」連結。

當客戶網頁頂端顯示彈出式面板時，位於彈出式面板下方之連結所屬的覆蓋圖，就會顯示在彈出式面板的頂端。

**問: 為什麼會遺失部分排名項目覆蓋圖?**

答: 有些排名連結會在頁面上隱藏 (例如子功能表連結)。因此也不會顯示其對應的連結覆蓋圖。因此您可以預期覆蓋圖排名會遺失部分特定的排名值，因為排名是針對頁面上的所有連結來進行計算 (顯示連結 + 隱藏連結)。

**問:「全部連結」報表中的連結排名是如何決定的?**

* 在「**漸層**」和「**氣泡**」模式中:「排名」是由量度欄決定。對於具有相同量度值的連結，再進一步根據連結 ID 的字母順序來排名。
* 而在「**獲益者和損失者**」模式中，排名主要是由「獲益 %」欄決定。對於具有相同獲益的連結，再進一步根據連結 ID 的字母順序來排名。

**問: 為什麼 Activity Map 執行時，沒有收集連結點擊資料?**

答: 使用 Activity Map 時，Analytics 標記不會收集連結點擊資料。此行為符合 ClickMap 外掛程式的行為。

**問: 為什麼量度下拉式清單多次列出相同的量度?**

答: Activity Map 會列出所有報表套裝的量度。因此，如果公司未執行[量度整合程序](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html)，可以預期會看到重複項目。

您可以利用量度下拉式清單，將計算量度清單限制為指派給已造訪頁面之報表套裝的量度。

**問:「Activity Map 全部連結報表」與「Reports &amp; Analytics Activity Map」報表有何差異?**

答: 若要提取 Activity Map 中的「全部連結報表」，我們會建立劃分請求，如下所示: Activity M ap 頁面 = "visitedpage"，依據`<list of link&regions present in the page at rendering time>`的 Activity Map 連結和地區來劃分。

若想在「Reports &amp; Analytics」中取得相等報表，您需先導覽至「Activity Map 頁面」報表。並在此處篩選 Activity Map 中的已造訪頁面名稱。已造訪頁面名稱會顯示在「Activity Map 頁面詳細資料底部面板」的左欄中。找到頁面後，即可從該頁面劃分，並選擇「Activity Map 連結和地區」做為第二維度。

不過，請務必注意，在「報告與分析」中取得的報表，會列出為該頁面收集的所有連結和地區。但 Activity Map 只會報告目前呈現在網頁中的連結和地區。所以，如果您擁有新聞網站，則只會顯示當下時間的新聞報導，而不會顯示當天稍早呈現的新聞報導。

**問: Activity Map 如何處理包含多個標記 (因此列出多個報表套裝) 的頁面?**

答: 依預設，Activity Map 會使用頁面所傳送第一個標記相關聯的報表套裝。

但您可透過「Activity Map 設定 &gt; 其他」索引標籤，選取其他已標記報表套裝。

**問: Activity Map 會掃描 Analytics 標記多久時間?**

答: 在頁面完成事件後，我們最多掃描 Analytics 標記 20 秒。

**問: Activity Map 如何處理動態內容?**

答: Activity Map 每 2 秒檢查一次，查看是否有如下所示的網頁狀態變更:

* HTML 內容變成可見
* HTML 內容變成隱藏
* 插入新的 HTML 內容

如果內容變成隱藏或顯示，應用程式會自動將受影響的連結狀態 (以及覆蓋圖) 從隱藏變更為顯示，或從顯示變更為隱藏。

如果插入新內容，應用程式會擷取關聯的連結、提取分析資料，並新增這些連結的覆蓋圖。

**問: 頁面流量報表是根據哪個量度?**

答: 所有顯示的資料都是根據頁面檢視。

**問: 可否說明各種頁面類型的 Activity Map 行為?**

*網頁沒有 Analytics 標記*

會在工具列底下顯示警告訊息，指出沒有標記。

*網頁具有不相容 Analytics 標記 (AppMeasurement v1.5 或更舊版本)*

系統會顯示訊息，指出您需要 (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) 將頁面代碼升級至 v1.6。

*網頁具有相容的 Analytics 標記 (AppMeasurement v1.6 或更新版本)，但未在管理工具中啟用 Activity Map*

系統會顯示警告訊息，指出您需要請管理員\[啟用 Activity Map 報表。\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md")

**問: 能否透過[Analytics 資料摘要](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)匯出 Activity Map 資料 (contextData)?**

答: 否。

## Activity Map 中的分段 {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**問: 區段關聯至個別使用者區段嗎? 共用管理員層級區段可否在 Activity Map 中使用?**

答: Activity Map 會繼承 Analytics 的管理員層級區段 (報表區段)。

**問: 區段可否用於即時模式?**

答: 否，區段不適用於即時模式。此功能等同於「Reports &amp; Analytics」中的即時報表。

## 虛擬報表套裝 {#section_BDB0CA9E732F478EAC349A79753A78DB}

**問: Activity Map 是否與虛擬報表套裝相容?**

答: 是。不過，由於虛擬報表套裝本身限制，Activity Map 的即時模式與虛擬報表套裝不相容。

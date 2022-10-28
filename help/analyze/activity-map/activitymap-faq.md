---
description: 在 Activity Map 中安裝、設定和使用功能的常問的問題。
title: Activity Map 常見問題集
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 0570bea923edc21a0f185f49fd6f604115d4a6e1
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 79%

---

# Activity Map 常見問題集

在 Activity Map 中安裝、設定和使用功能的常問的問題。

+++所有Analytics客戶都有權存取管理工具的「ActivityMap啟用」頁面嗎？
凡是擁有 Adobe Analytics Standard、Premium 和 Ultimate 合約的組織，都可以存取 Activity Map。
+++

+++Activity Map如何支援單頁應用程式(SPA)?
Activity Map 每隔幾秒鐘會掃描網頁一次，查看頁面是否有變更。 Activity Map 會尋找頁面上的新內容，而不需要載入新頁面，但這個新內容始終歸因於頁面載入時所找到的第一個 pageName。

* Activity Map 會查看它所知道的連結的可見度是否已變更。 如果發現可見度有變更，則該連結的「頁面上連結」表格的「存在」欄會以[!UICONTROL 已顯示]或[!UICONTROL 已隱藏]來更新。

* 當使用者互動建立新內容時，AppMeasurement 找到的任何新元素如果是連結，則會新增到[!UICONTROL 頁面上連結]表格中。 Activity Map 會傳送包含這些新連結的新資料要求。 當資料要求是由 UI 進行處理時，新連結應該會出現在[!UICONTROL 頁面上連結]表格中。
+++

+++Activity Map是否提供「檢視」的資料？
否，Adobe 不會追蹤已檢視的連結。
+++

+++Activity Map支援哪些瀏覽器和版本？
Activity Map 支援最新版本的最新瀏覽器。
+++

+++Activity Map是否會增加伺服器呼叫？
Activity Map 本身不會傳送伺服器呼叫。Activity Map 內文資料變數會隨 Analytics 頁面檢視呼叫包含在後續頁面上。
+++

+++為何遺失部分排名項目覆蓋圖？
有些排名連結 (例如子功能表連結) 會隱藏在頁面中。因此也不會顯示其對應的連結覆蓋圖。排名會計算頁面上所有連結，包括隱藏的連結。
+++

+++ 「全部連結」報表中的連結排名如何決定?**
* **在「漸層」和「氣泡」模式中**：「排名」是由量度欄決定。對於具有相同量度值的連結，再進一步根據連結 ID 的字母順序來排名。
* **在「獲益者和損失者」模式中**：排名主要是由「獲益 %」欄決定。對於具有相同獲益的連結，再進一步根據連結 ID 的字母順序來排名。
+++

+++Activity Map如何處理使用多個報表套裝的頁面？
依預設，Activity Map 會使用與頁面所傳送第一個標記相關聯的報表套裝。但您可透過「**[!UICONTROL Activity Map 設定]** > **[!UICONTROL 其他]**」索引標籤，選取其他已標記報表套裝。
+++

+++Activity Map會掃描頁面上的Adobe Analytics多久？
在頁面完成事件後，Activity Map 會掃描長達 20 秒以查看 Adobe Analytics 是否存在。
+++

+++Activity Map如何處理動態內容？
Activity Map 每 2 秒檢查一次，查看是否有如下所示的網頁狀態變更：

* HTML 內容變成可見
* HTML 內容變成隱藏
* 插入新的 HTML 內容

如果內容變成隱藏或顯示，應用程式會自動將受影響的連結狀態 (以及覆蓋圖) 從隱藏變更為顯示，或從顯示變更為隱藏。如果插入新內容，應用程式會擷取關聯的連結、提取分析資料，並新增這些連結的覆蓋圖。
+++

+++ 「頁面流量」報表是根據哪個量度？
所有顯示的資料都是以頁面檢視次數為準。
+++

+++我可以透過資料摘要匯出Activity Map內容資料變數嗎？
是。此 [資料欄](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) Activity Map使用的 `clickmaplink`, `clickmaplinkbyregion`, `clickmappage`，和 `clickmapregion`.
+++

+++區段可否用於即時模式？
否，區段不適用於即時模式。此功能等同於 Reports &amp; Analytics 中不支援區段的即時報告。
+++

+++Activity Map是否與虛擬報表套裝相容？
可以。不過，由於虛擬報表套裝本身限制，Activity Map 的即時模式與虛擬報表套裝不相容。
+++

+++如何停用Activity Map?
您有三種選項:

* 從 JS 檔刪除 `AppMeasurement_Module_ActivityMap` 功能
* 例如，透過空白內文新增重寫上述函數的自訂程式碼:

   ```js
   function AppMeasurement_Module_ActivityMap() {}
   ```

* 透過設定 `s.trackClickMap` 和 `s.trackInlineStats` 到 `false` 來設定 AppMeasurement 
+++

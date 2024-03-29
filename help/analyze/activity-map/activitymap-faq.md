---
description: 在 Activity Map 中安裝、設定和使用功能的常問的問題。
title: Activity Map 常見問題集
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---

# Activity Map 常見問題集

在 Activity Map 中安裝、設定和使用功能的常問的問題。

+++所有 Analytics 客戶都可以存取「管理工具 ActivityMap 啟用」頁面嗎？
凡是擁有 Adobe Analytics Standard、Premium 和 Ultimate 合約的組織，都可以存取 Activity Map。
+++

+++Activity Map 如何支援單頁應用程式 (SPA)？
Activity Map 每隔幾秒鐘會掃描網頁一次，查看頁面是否有變更。Activity Map 會尋找頁面上的新內容，而不需要載入新頁面，但這個新內容始終歸因於頁面載入時所找到的第一個 pageName。

* Activity Map 會查看它所知道的連結的可見度是否已變更。如果發現可見度有變更，則該連結的「頁面上連結」表格的「存在」欄會以[!UICONTROL 已顯示]或[!UICONTROL 已隱藏]來更新。

* 當使用者互動建立新內容時，AppMeasurement 找到的任何新元素如果是連結，則會新增到[!UICONTROL 頁面上連結]表格中。Activity Map 會傳送包含這些新連結的新資料要求。當資料要求是由 UI 進行處理時，新連結應該會出現在[!UICONTROL 頁面上連結]表格中。
+++

+++Activity Map 是否提供「檢視次數」的資料？
否，Adobe 不會追蹤已檢視的連結。
+++

+++Activity Map 支援哪些瀏覽器和版本？
Activity Map 支援最新版本的最新瀏覽器。
+++

+++Activity Map 是否會增加伺服器呼叫？
Activity Map 本身不會傳送伺服器呼叫。Activity Map 內文資料變數會隨 Analytics 頁面檢視呼叫包含在後續頁面上。
+++

+++為什麼缺少部分排名項目覆蓋圖？
有些排名連結 (例如子功能表連結) 會隱藏在頁面中。因此也不會顯示其對應的連結覆蓋圖。排名會計算頁面上所有連結，包括隱藏的連結。
+++

+++「全部連結」報告中的連結排名是如何決定的？**
* **在「漸層」和「氣泡」模式中**：「排名」是由量度欄決定。對於具有相同量度值的連結，再進一步根據連結 ID 的字母順序來排名。
* **在「獲益者和損失者」模式中**：排名主要是由「獲益 %」欄決定。對於具有相同獲益的連結，再進一步根據連結 ID 的字母順序來排名。
+++

+++Activity Map 如何處理使用多個報告套裝的頁面？
依預設，Activity Map 會使用與頁面所傳送第一個標記相關聯的報表套裝。但您可透過「**[!UICONTROL Activity Map 設定]** > **[!UICONTROL 其他]**」索引標籤，選取其他已標記報表套裝。
+++

+++Activity Map 在頁面上掃描 Adobe Analytics 多久了？
在頁面完成事件後，Activity Map 會掃描長達 20 秒以查看 Adobe Analytics 是否存在。
+++

+++Activity Map 如何處理動態內容？
Activity Map 每 2 秒檢查一次，查看是否有如下所示的網頁狀態變更：

* HTML 內容變成可見
* HTML 內容變成隱藏
* 插入新的 HTML 內容

如果內容變成隱藏或顯示，應用程式會自動將受影響的連結狀態 (以及覆蓋圖) 從隱藏變更為顯示，或從顯示變更為隱藏。如果插入新內容，應用程式會擷取關聯的連結、提取分析資料，並新增這些連結的覆蓋圖。
+++

+++頁面流量報告是以哪個量度為準？
所有顯示的資料都是以頁面檢視次數為準。
+++

+++我是否可透過資料摘要匯出 Activity Map 內容資料變數？
是。Activity Map 使用的[資料欄](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)為 `clickmaplink`、`clickmaplinkbyregion`、`clickmappage` 和 `clickmapregion`。
+++

+++區段是否適用於即時模式？
否，區段不適用於即時模式。
+++

+++Activity Map 是否可與虛擬報表套裝相容？
是。不過，由於虛擬報表套裝本身限制，Activity Map 的即時模式與虛擬報表套裝不相容。
+++

+++我如何才能停用 Activity Map？
您有三種選項:

* 從 JS 檔刪除 `AppMeasurement_Module_ActivityMap` 功能
* 例如，透過空白內文新增重寫上述函數的自訂程式碼:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

* 透過設定 `s.trackClickMap` 和 `s.trackInlineStats` 到 `false` 來設定 AppMeasurement 
+++

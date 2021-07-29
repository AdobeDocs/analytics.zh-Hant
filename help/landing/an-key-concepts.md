---
description: 本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。
title: Adobe Analytics - 重要概念
exl-id: 359c6663-33fd-4491-8ea0-55cd9ae31859
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '1815'
ht-degree: 99%

---

# Adobe Analytics - 重要概念

本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。

## Analytics 工具 {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 產品 | 說明 | 文件連結 |
| --- | --- | --- |
| Analysis Workspace | 用於建立強大、自訂的分析專案，並讓使用者都能自行獲得深入分析的瀏覽器解決方案。提供比 Reports and Analytics 更高的報表靈活性。 | [Analysis Workspace 首頁](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics (原 SiteCatalyst) | 用於報告和分析的瀏覽器解決方案。Analytics 套裝中的入門工具。 | [Reports and Analytics 首頁](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | 可讓您從 Adobe Analytics 資料建立自訂請求，並使用 Microsoft Excel 加以視覺化的 Excel 增益集。 | [Report Builder 首頁](/help/analyze/report-builder/home.md) |
| Data Workbench (前稱為 Insight) | 專門設計來收集、處理、分析以及呈現多個管道的線上和離線客戶互動情形。 | [Data Workbench 用戶端](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=zh-Hant) |
| Data Warehouse | 用於儲存和自訂報表的原始、未處理資料複本，可供您透過篩選資料的方式來執行。非點擊層級。 | [Data Warehouse 首頁](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | 將整個 Adobe Experience Cloud 上行動應用程式的行動行銷功能集合在一起，讓您了解並改進使用者與應用程式的互動。 | [Mobile Services 首頁](https://experienceleague.adobe.com/docs/mobile-services/using/home.html?lang=zh-Hant) |
| Adobe Exchange資料連接器(前身為 Genesis) | 從協力廠商應用程式匯入追蹤資料至 Analytics，以便在同一中央位置呈現端對端的效能資訊。Adobe 計畫自 2021 年 8 月 1 日起終止 Data Connector 整合服務。 | [資料連接器首頁](/help/import/data-connectors/data-connectors-eol.md) |
| Adobe Experience Platform中的標籤 | Adobe 推出的下一代網站標籤與行動 SDK 管理功能。 | [標籤概述](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) |

## 重要術語 {#concept_E473ACBB8E4A42B4AC005538AC12F154}

按一下[此處](/help/technotes/terms.md)可存取 Adobe Analytics 術語的擴充詞彙表。

| 詞語 | 說明 | 文件連結 |
| --- | --- | --- |
| Prop (自訂流量) | 用於追蹤逐頁網站流量活動的維度。Prop 無法在頁面間持續存在。流量變數的主要應用範圍： <ul> <li>透過簡單計數，找出「最熱門」的特定值</li> <li>可清楚掌握使用者前往網站的路徑</li> </ul> <br> 流量變數的範例：頁面名稱、網站區域、瀏覽器 | [Prop](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar (自訂轉換) | 會按照您自訂的時間留存的維度。有效期選項包括事件有效期、瀏覽有效期或 X 天有效期，且應由該變數上執行的分析類型來驅動。<br> eVar 和 prop 之間的主要差異： <ul> <li>Prop 通常用於路徑分析，因為系統不會移除持續性。</li> <li>eVar 通常用於轉換分析。</li> </ul> <br> 轉換變數範例：內部搜尋詞、內部促銷、外部促銷活動 (s.campaign) | [eVar](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| 事件/量度 (s.events) | 用於測量訪客在網站上採取所需關鍵動作的量度。有 3 種事件類型：計數器、數值和貨幣。事件新增至轉換變數 (eVar) 報表時最為有用。eVar 可提供關於所發生情形的質化資訊，事件則可提供關於所發生情形的量化資訊。<br> eVar 和事件之間的主要差異： <ul> <li>eVar 有助於了解影響轉換的人、事、物資訊</li> <li>事件用於測量發生的轉換次數</li> </ul> <br> 轉換事件範例：訂購、應用程式啟動、銷售機會、收入。 | [事件](/help/admin/admin/c-success-events/success-event.md) |
| 元件 | 您可以拖放至專案上的維度、量度、區段和時間詳細程度 (日期範圍)。 | [元件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| 維度 | eVar、prop、分類和標準 Adobe 收集值的集合。 | [維度](/help/components/dimensions/overview.md) |
| 量度 | 實作事件和計算量度的集合。 | [量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| 計算量度 | 能夠透過您的實作項目所擷取的現有量度中衍生出自訂量度。 | [計算量度](/help/components/c-calcmetrics/cm-overview.md) |
| 區段 | 能夠建立、管理、共用並套用功能強大且目標專一的對象區段至 Analytics 報表。區段會在 Analytics 產品間共用，也能在 Experience Cloud 間共用。 | [區段](/help/components/segmentation/seg-home.md) |
| 時間 (日期範圍) | 能夠將日期篩選為任何時段，並建立可在分析中重複使用的自訂日期範圍。 | [日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| 視覺效果 | 豐富的視覺效果，可讓專案中的資料更加生動。 | [視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| 組織 | 可限制專案或虛擬報表套裝中可存取的元件。 | [VRS 策劃](/help/components/vrs/vrs-components.md) <br> [專案策劃](/help/analyze/analysis-workspace/curate-share/curate.md) |

## 重要報表

| 報表 | 說明 | 文件連結 |
| --- | --- | --- |
| 維度/報表完整清單 | Adobe Analytics 中所有可用維度/報表的定義。 | [維度](/help/components/dimensions/overview.md) |
| Advertising Analytics | 在 Adobe Analytics 中以並排方式分析所有 Google 和 Bing 付費搜尋資料。透過廣告平台、關鍵字、比對類型等整合項目建立維度。所建立的量度為 AMO 曝光、AMO 點擊、AMO 成本、平均排名和平均品質分數。 | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | 透過 AAM 中使用者的對象成員資格，使傳入的 Analytics 點擊更為豐富。您可以在 Analytics 工作流程中納入 (AAM) 對象資料，如人口資訊 (例如性別或收入等級)、心理變數資訊 (例如興趣及嗜好)、CRM 資料或廣告曝光資料。透過這項整合建立的維度為對象 ID與對象名稱。 | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| 歸因 IQ | 可讓您了解如何在客戶歷程中進行有意義的參與，聰明地找出將客戶導向目標結果的轉折點，並有效提升行銷活動的效能。可用模型包括初次、最後一次、線性、參與率、J 形、反向 J 形、U 形、同一次接觸、自訂和時間耗損。 | [歸因 IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| 異常偵測 | 一種比較指定量度和先前資料的統計方法，可用於判斷兩者差異。在 Analysis Workspace 中，已將針對所有趨勢視覺效果的異常偵測預設為啟用。 | [異常偵測](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| 貢獻分析 | 藉由對您可存取的每個單一量度和維度執行自動分析，探索異常背後的「原因」。 | [貢獻分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| 同類群組分析 | 同類群組是指一段指定時間內，共享相同特徵的一組人。同類群組分析有助於分析使用者的保留率和流失率。 | [同類群組分析](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| 客戶歷程報表 | 顯示使用者瀏覽您的網站或應用程式時所採取路徑的相關資訊。Prop、eVar 和事件可在 Analysis Workspace 中使用這項分析。 | [Analysis Workspace 流失](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Analysis Workspace 流量](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Reports and Analytics 路徑分析](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| 行銷管道 | 這些報表可協助您理解哪些外部管道將使用者引入您的網站，以及在促進轉換方面哪些管道最有效。並提供首次接觸和上次接觸歸因檢視。這是 Adobe Analytics 慣用的外部流量來源報表 (優先於促銷活動或流量來源)，因為這可同時提供付費和自然管道的最全面資訊。 | [行銷管道](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| 行動 | 顯示從行動裝置或平板電腦存取的網站相關資訊。 | [行動報表](/help/components/dimensions/mobile-dimensions.md) |
| 行動應用程式 | 顯示行動應用程式的相關基本使用資訊。我們的 SDK 一經實作並開啟報告功能後，這些報表就可供使用。此外，Adobe Mobile Services 已建立單獨的行動應用程式介面，可提供更完整的應用程式資料，讓您了解並改進使用者對您應用程式的互動程度。 | [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) |
| 產品 | 識別個別產品和產品群組 (類別) 對各種轉換量度 (如收入或結帳) 的貢獻度。 | [產品報表](/help/components/dimensions/product.md) |
| 區段比較 | 透過自動分析您可以存取的每個單一量度和維度，找出不同區段之間在統計上最顯著的差異。 | [區段比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| 網站內容報表 | 顯示您網站中最活躍的網頁與區域，以及最常用的伺服器。 | [網站內容報表](/help/components/dimensions/page.md) |
| 網站量度報表 | 顯示您網站的相關量化資訊，例如獨特訪客、訂購、收入等。每個量度都能放在其他項目型報表中。 | [網站量度報表](/help/components/metrics/overview.md) |
| 訪客資料 | 協助您了解不同資料類別 (包括國家、州、ZIP/郵遞區號和網域) 之客戶的購買模式。 | [訪客資料](/help/components/dimensions/language.md) |
| 訪客保留率 | 顯示客戶忠誠度的相關資訊，例如有多少訪客回訪您的網站以及回訪頻率。 | [訪客保留率](/help/components/dimensions/customer-loyalty.md) |
| 專案連結、共用與排程 | 在 Analytics 介面中儲存和/或與他人共用您的工作的方法。 | [傳送及排程檔案](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## 關鍵量度 {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 量度名稱 | 定義 | 文件連結 |
| --- | --- | --- |
| 完整量度清單 | Adobe Analytics 中所有量度的定義。 | [量度概觀](/help/components/metrics/overview.md) |
| 不重複訪客 | 在指定時段內，前往網站的不重複訪客數量。 | [不重複訪客](/help/components/metrics/unique-visitors.md) |
| 瀏覽 | 某一段時間的頁面檢視順序。瀏覽開始於一個人開始檢視網站的某個頁面，結束於閒置 30 分鐘後。 | [瀏覽](/help/components/metrics/visits.md) |
| 頁面檢視 | 當訪客檢視您的網站頁面時就會發生頁面檢視。 | [頁面檢視](/help/components/metrics/page-views.md) |
| 例項 | 變數被定義的次數。每一次 Adobe Analytics 查看變數中的值時，該對應報表中的例項就會遞增一。 | [例項](/help/components/metrics/instances.md) |
| 發生次數 | 變數經定義或延續使用的次數。 | [發生次數](/help/components/metrics/occurrences.md) |

## 匯入選項 {#concept_7C6DF03B5F9149E2A77F36C739432059}

| 選項 | 說明 | 文件連結 |
| --- | --- | --- |
| 分類匯入工具 | 透過瀏覽器或 FTP 上傳，根據擷取的維度匯入中繼資料。相較於規則產生器，此為手動方式。 | [分類匯入工具](/help/components/classifications/importer/c-working-with-saint.md) |
| 規則產生器 | 根據使用者定義規則，自動建立維度的中繼資料分類。 | [分類規則產生器](/help/components/classifications/crb/classification-rule-builder.md) |
| 客戶屬性 | 上傳至 Experience Cloud 供 Adobe Analytics 和 Adobe Target 使用的 CRM 資料。 | [客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hant) |
| 資料來源 | 可根據維度或僅依日期匯入離線量度至 Analytics。 | [資料來源](/help/import/c-data-sources/datasrc-home.md) |
| Adobe Exchange資料連接器 | 請參閱 [Analytics 工具](/help/import/data-connectors/data-connectors-eol.md) |  |
| 原生整合 | 對象分析與廣告分析。 | 請參閱「關鍵報表」區段。 |

## 匯出選項 {#concept_C62B688E259141CF92C048E8110464BE}

| 選項 | 說明 | 文件連結 |
| --- | --- | --- |
| UI 下載與排程 | 從 Analysis Workspace 將資料匯出為 CSV 或 PDF | [下載 PDF 或 CSV 檔案](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | 請參閱 Analytics 工具。 |  |
| Analytics API | 建立對 Analytics 資料的自訂查詢。 | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | 請參閱 Analytics 工具。 |  |
| Analytics 資料摘要 | 從 Analytics 取得資料的最詳細方式。設定 Analytics 的點擊層級回饋。 | [Analytics 資料摘要](/help/export/analytics-data-feed/data-feed-overview.md) |

## 資料彙集與驗證 {#concept_E07350D4CA5047DAA7D81F762F29606A}

| 方法/資源 | 說明 | 文件連結 |
| --- | --- | --- |
| 開發人員資源 | 概述可用於收集所有可用平台 (網路、行動應用程式、視訊、Flash 等) 之 Analytics 資料之程式庫的文件 | [開發人員文件](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| 實作指南 | 說明資料收集變數，並詳述如何在 JavaScript 中實作資料收集程式碼。 | [實作指南](/help/implement/home.md) |
| App Measurement (s_code) | 全域變數管理 | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| 應用程式 SDK | 可自訂套裝，包含應用程式設定檔的預先填入版本。 | <ul><li>[iOS 應用程式](https://experienceleague.adobe.com/docs/mobile-services/ios/overview.html?lang=zh-Hant)</li><li>[Android](https://experienceleague.adobe.com/docs/mobile-services/android/getting-started-android/requirements.html?lang=zh-Hant)</li></ul> |
| Adobe Experience Platform中的標籤 | 請參閱 Analytics 工具。 |  |
| VISTA | 可讓您套用伺服器端邏輯，以便在收集資料時變更或分段資料。 | [VISTA 規則](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| 處理規則 | 能夠在 Analytics UI 中設定、修改與複製變數，以便變更所收集的資料。 | [處理規則](/help/admin/admin/c-processing-rules/processing-rules.md) |
| 除錯工具選項 | 具備數個除錯程式和封包 Sniffer 可協助驗證您的實作情形，其中包括 Adobe Experience Cloud Debugger。 | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| 資料插入 API | 資料插入 API 提供的機制，可用於伺服器端資料收集與將資料提交至 Experience Cloud 伺服器。伺服器端資料收集僅會根據網站瀏覽器的要求和網站伺服器的回應收集資料，不會使用每個網頁上的 JavaScript 信標來將訪客資料傳輸至 Experience Cloud 伺服器。 | [透過 POST 實作 Adobe Analytics 資料插入 API 的步驟](https://helpx.adobe.com/tw/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |

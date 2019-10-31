---
description: 本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。
seo-description: 本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。
seo-title: Adobe Analytics - 重要概念
title: Adobe Analytics - 重要概念
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Adobe Analytics - 重要概念

本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 產品 | 說明 | 文件連結 |
|--- |--- |--- |
| Analysis Workspace | 建立強穩、自訂分析專案並讓見解大眾化的瀏覽器解決方案。 提供比「報告與分析」更多的報表彈性 | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Report &amp; Analytics (前稱為 SiteCatalyst) | 用於報告和分析的瀏覽器解決方案。 Analytics 套裝中的入門工具。 | [報告與分析首頁](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Excel增益集可讓您從Adobe Analytics資料建立自訂請求，並使用Microsoft excel視覺化請求。 | [報告建立工具首頁](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis (前稱為 Discover) | 進階數位分析的Java工具。 | [臨機分析首頁](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench (前稱為 Insight) | 專門設計來收集、處理、分析以及呈現多個管道的線上和離線客戶互動情形。 | [資料工作台用戶端](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | 用於儲存和自訂報表的原始、未處理資料複本，可供您透過篩選資料的方式來執行。非點擊層級。 | [資料倉庫首頁](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | 將整個 Adobe Experience Cloud 上行動應用程式的行動行銷功能集合在一起，讓您瞭解並改進使用者與應用程式的互動。 | [Mobile services首頁](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors（先前稱為Genesis） | 從協力廠商應用程式將追蹤資料匯入Analytics，讓端對端可在單一集中位置檢視效能。 | [資料連接器首頁](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| 動態標籤管理 (DTM) | 可讓您管理所有網站上的分析、目標及其他標籤，不受網域數目影響。 | [DTM首頁](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Adobe提供新一代的網站標籤和行動SDK管理功能。 | [Adobe Launch首頁](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

按一下[此處](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html)可存取 Adobe Analytics 術語的擴充詞彙表。

| 詞語 | 說明 | 文件連結 |
|--- |--- |--- |
| Prop（自訂流量） | 用於追蹤逐頁網站流量活動的維度。 Prop 無法在頁面間持續存在。流量變數的主要應用範圍: <ul><li>輕鬆計數以尋找特定值的「最受歡迎」</li><li>洞悉使用者在您網站中的路徑分析 </li></ul><br>流量變數的範例：頁面名稱、網站區域、瀏覽器</br> | [Prop](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar（自訂轉換） | 維度會持續一段您自訂的時間。 有效期選項包括事件有效期、瀏覽有效期或 X 天有效期，且應由該變數上執行的分析類型來驅動。<br>eVar和prop之間的主要差異：</br><ul><li>Prop通常用於路徑分析，因為會移除永續性。</li><li>eVar通常用於轉換分析。</li></ul><br>轉換變數的範例：內部搜尋詞、內部促銷、外部促銷活動(s.campaign)</br> | [eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| 事件／量度(s.events) | 度量我們希望訪客在網站上執行的關鍵動作。 有 3 種事件類型: 計數器、數值和貨幣。事件新增至轉換變數 (eVar) 報表時最為有用。eVar 可提供關於所發生情形的質化資訊，事件則可提供關於所發生情形的量化資訊。<br>eVar和事件之間的主要差異：</br><ul><li>eVar會告訴我們誰、什麼或哪些影響轉換</li><li>事件會測量發生多少轉換</li></ul><br>轉換事件範例: 訂購、應用程式啟動、銷售機會、收入。</br> | [事件](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| 元件 | 維度、量度、區段和時間粒度（日期範圍），您可以拖放至專案上。 | [元件](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| 維度 | eVar、prop、分類和標準Adobe收集值的集合。 | [維度](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| 量度 | 實作事件和計算量度的集合。 | [量度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| 計算量度 | 能夠從透過您的實施所擷取的現有量度衍生自訂量度。 | [計算量度](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| 區段 | 能夠建立、管理、共用並套用功能強大且目標專一的對象區段至 Analytics 報表。區段會在 Analytics 產品間共用，也能在 Experience Cloud 間共用。 | [區段](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| 時間（日期範圍） | 能夠將日期篩選為任何時段，並建立可在分析中重複使用的自訂日期範圍。 | [日期範圍](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| 視覺效果 | 豐富的視覺效果，可協助您讓專案中的資料更生動。 | [視覺效果](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| 組織 | 可限制專案或虛擬報表套裝中可存取的元件。 | [VRS組](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[織專案組](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[織比較](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## 關鍵報告

| 報告 | 說明 | 文件連結 |
|--- |--- |--- |
| 維度/報表完整清單 | Adobe Analytics 中所有可用維度/報表的定義。 | [維度](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Advertising Analytics | 在Adobe Analytics中並排分析您的所有Google和Bing付費搜尋資料。 透過整合建立的維度包括廣告平台、關鍵字、符合類型等。 建立的量度包括AMO印象、AMO點按、AMO成本、平均 位置和平均 品質分數。 | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | 在AAM中使用者的讀者會籍，豐富傳入的Analytics點擊。 您可以將AAM受眾資料，例如人口統計資訊（例如性別或收入等級）、心理變數資訊（例如興趣和嗜好）、CRM資料和廣告曝光資料，併入任何Analytics工作流程。 透過此整合建立的維度為「對象ID與對象名稱」。 | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| 歸因 IQ | 讓您瞭解客戶歷程中有意義的互動如何發生，智慧地識別轉折點，引導客戶達成目標，有效地最佳化行銷活動。 模型包括第一、最後、線性、參與、j形、逆j形、u形、相同觸摸、自訂和時間衰減。 | [歸因 IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| 異常偵測 | 一種統計方法，用以判斷指定量度與先前資料的變更方式。 分析工作區中所有趨勢視覺化預設會開啟廣告。 | [異常偵測](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| 貢獻分析 | 透過對您可存取的每個度量和維度執行自動分析，探索異常背後的「原因」。 | [貢獻分析](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| 同類群組分析 | 同類群組是指在指定期間有共同特徵的一群人。 世代分析有助於分析使用者的保留率和流失率。 | [同類群組分析](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| 客戶歷程報告 | 顯示使用者瀏覽您網站或應用程式時的路徑相關資訊。 Prop、eVar和事件可用於分析工作區的此分析。 | [分析工作區流](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[失分析工作區](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[流量報告與分析路徑](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| 行銷管道 | 這些報表可協助您理解哪些外部管道將使用者引入您的網站，以及在促進轉換方面哪些管道最有效。並提供首次接觸和上次接觸歸因檢視。這是 Adobe Analytics 慣用的外部流量來源報表 (優先於促銷活動或流量來源)，因為這可同時提供付費和自然管道的最全面資訊。 | [行銷管道](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| 行動 | 顯示從行動裝置或平板電腦存取的網站相關資訊。 | [行動報表 | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| 行動應用程式 | 顯示行動應用程式的相關基本使用資訊。我們的 SDK 一經實施並開啟報告功能後，這些報表就可供使用。此外，Adobe Mobile Services 已建立單獨的行動應用程式介面，可提供更完整的應用程式資料，讓您了解並改進使用者對您應用程式的互動程度。在這裡存取 [介面](https://mobilemarketing.adobe.com)。 | [Adobe Mobile 服務](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | 產品 | 識別個別產品和產品群組 (類別) 對各種轉換量度 (如收入或結帳) 的貢獻度。 | [產品報告](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| 區段比較 | 透過自動分析您可存取的每個單一度量和維度，發現群體之間在統計上最顯著的差異。 | [區段比較](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| 網站內容報表 | 顯示您網站中最活躍的網頁與區域，以及最常用的伺服器。 | [網站內容報表](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| 網站度量報表 | 顯示您網站的相關量化資訊，例如獨特訪客、訂購、收入等。每個量度都能放在其他項目型報表中。 | [網站度量報表](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| 訪客資料 | 協助您瞭解不同資料類別 (包括國家、州、ZIP/郵遞區號和網域) 之客戶的購買模式。 | [訪客資料](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| 訪客保留率 | 顯示客戶忠誠度的相關資訊，例如有多少訪客回訪您的網站以及回訪頻率。 | [訪客保留率](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| 專案連結、共用與排程 | 在 Analytics 介面中儲存和/或與他人共用您的工作的方法。 | [傳送和排程檔案](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 量度名稱 | 定義 | 文件連結 |
|---|---|---|
| 完整量度清單 | Adobe Analytics 中所有量度的定義。 | [量度概觀](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| 不重複訪客 | 在指定時段內，前往網站的不重複訪客數量。 | [不重複訪客](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| 瀏覽 | 某一段時間的頁面檢視順序。瀏覽開始於一個人開始檢視網站的某個頁面，結束於閒置 30 分鐘後。 | [瀏覽](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| 頁面檢視 | 當訪客檢視您的網站頁面時就會發生頁面檢視。 | [頁面檢視](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| 例項 | 變數被定義的次數。每一次 Adobe Analytics 查看變數中的值時，該對應報表中的例項就會遞增一。 | [例項](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| 發生次數 | 變數的定義或持續次數。 | [發生次數](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## 匯入選項 {#concept_7C6DF03B5F9149E2A77F36C739432059}

| 選項 | 說明 | 文件連結 |
|---|---|---|
| 分類匯入工具 | 透過瀏覽器或 FTP 上傳，根據擷取的維度匯入中繼資料。相較於規則產生器，此為手動方式。 | [分類匯入工具](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| 規則產生器 | 根據使用者定義規則，自動建立維度的中繼資料分類。 | [分類規則產生器](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| 客戶屬性 | 上傳至Experience cloud以用於Adobe Analytics和Adobe Target的CRM資料。 | [客戶屬性](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| 資料來源 | 依據維度或依日期將離線量度匯入Analytics。 | [資料來源](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Adobe Exchange資料連接器 | 請參閱 [Analytics工具](/help/landing/an-key-concepts.md) |  |
| 原生整合 | 受眾分析與廣告分析。 | 請參閱「關鍵報表」區段。 |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| 選項 | 說明 | 文件連結 |
|---|---|---|
| UI下載與排程 | 從分析工作區匯出資料為CSV或PDF | [下載 PDF 或 CSV 檔案](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | 請參閱Analytics工具。 |
| Analytics API | 建立對 Analytics 資料的自訂查詢。 | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | 請參閱Analytics工具。 |  |
| Analytics 資料摘要 | 從 Analytics 取得資料的最詳細方式。設定 Analytics 的點擊層級回饋。 | [Analytics 資料摘要](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| 方法/資源 | 說明 | 文件連結 |
|--- |--- |--- |
| 開發人員資源 | 概述可用於收集所有可用平台 (網路、行動應用程式、視訊、Flash 等) 之 Analytics 資料之程式庫的文件 | [開發人員檔案](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| 實施指引 | 說明資料收集變數，並詳述如何在 JavaScript 中實施資料收集程式碼。 | [實施指南](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| App Measurement (s_code) | 全域變數管理 | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| 應用程式 SDK | 可自訂套裝，包含應用程式設定檔的預先填入版本。 | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM和Adobe Launch | 請參閱Analytics工具。 |  |
| VISTA | 可讓您套用伺服器端邏輯，在收集資料時變更或分段資料。 | [VISTA 規則](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| 處理規則 | 能夠在Analytics UI中設定、修改和複製變數，以變更收集的資料。 | [處理規則](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| 除錯工具選項 | 有數個除錯程式和封包Sniffer可協助驗證您的實作，包括Adobe Experience cloud除錯程式。 | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| 資料插入 API | 資料插入API提供伺服器端資料收集和提交至Experience cloud伺服器的機制。 伺服器端資料收集僅根據網頁瀏覽器要求和網頁伺服器回應收集資料，而不是使用每個網頁上的JavaScript信標將訪客資料傳輸至Experience cloud伺服器。 | [使用POST實作Adobe Analytics資料插入API的步驟](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |

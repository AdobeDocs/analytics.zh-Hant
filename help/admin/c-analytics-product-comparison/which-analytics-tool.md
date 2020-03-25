---
description: 此說明頁面包含每個Adobe Analytics工具的建議使用案例。 工具的列出順序應視為工具。 如果某個工具不滿足需求，請移至下一個工具以供考慮。
title: 我該使用哪種 Adobe Analytics 工具呢？
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: tm+mt
source-git-commit: f7125e6845a653ca3d4dd3f1313d1b39f564459c

---


# 我該使用哪種 Adobe Analytics 工具呢？

此說明頁面包含每個Adobe Analytics工具的建議使用案例。 工具的列出順序應視為工具。 如果某個工具不滿足需求，請移至下一個工具以供考慮。

如需Adobe Analytics產品比較的詳細資訊，請前 [往](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md)。

## Adobe Analytics 報告使用者介面 {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**應該是滿足您所有報告和分析需求的首選使用者介面。Adobe 繼續投資該產品並發行每月更新。如果在 Analysis Workspace 中有無法執行的任務，請考慮以下其他介面。**

該使用 **[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**的情況：

* 入門使用者需要存取預先建立的報告以便導覽。
* 若要瞭解Target活動(Analytics for Target/A4T)提升度和可信度。
* 在UI中存取即時資料。
* 若要設定日曆事件。
* 若要設定目標。
* 若要檢視機器人報告。
* 若要存取「並行檢視器」、「視訊日期部分」和「檢視器下拉」的獨特視訊視覺化。
* 若要在排程報表中運用發佈清單。

該使用 **[Mobile Services UI](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)**的情況：

* 如果需要孤立的行動應用程式資料檢視。
* 若要管理您行動應用程式 SDK 的實作。
* 若要設定行動廣告，例如應用程式內訊息、推播訊息和位置定位。
* 如果需要更多互動式視覺化來呈現應用程式資料（散射環）。
* 在地圖上視覺化地標。
* 適用於期限值量度。

該使用 **[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**的情況：

* 要導出50,000行資料
* 如果需要項目工作的標籤組織。
* 若要使用網站分析報表（3D路徑報表）。

該使用 **[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**的情況：

* 作為最有彈性的Analytics工具選項（直至訪客層級、點擊層級分析）。
* 建立從CRM到POS到Web的線上與離線互動的多頻道資料集。
* 適用於進階歸因（規則型和演算法模型）。
* 針對預測性、統計模型（傾向分數、叢集、關聯等）。
* 用於延遲分析（事件之前／之後的時間）。
* 用於識別和匯出整個Adobe Experience Cloud中的複雜區段。

## 將資料匯入Adobe Analytics {#section_B42B998D6E3E4357B024AEFA4EC69A23}

該使用&#x200B;**[「分類」](/help/components/c-classifications2/c-classifications.md)**的情況：

* 當您有要與收集值（eVar、prop、行銷渠道）關聯的中繼資料時
* 選項：

   * 規則產生器：您已針對變數，收集可預測的格式化值 (例如，具有分隔符號的值) 時使用。此方法可讓您設定規則一次，基本上可以「設定並忘記」。
   * 瀏覽器匯入器：如果您沒有可預測的值，或您有需要執行一次性更新的有限值清單，請使用此工具。此方法需要您不斷監控新值的分類。

該使用「**[資料來源](/help/import/c-data-sources/datasrc-home.md)**」的情況：

* 有您想要永久寫入 Adobe Analytics 中的離線資料時
* 選項：

   * 摘要：輕鬆上傳資料，按日期或有限的維度
   * 交易 ID：上傳會將線上端點連線到離線資料的資料，並將匯入的資料完全關聯到線上擷取的訪客快照 (例如，線上完成訂單，然後離線辦理退款)
   * 完整處理：具有時間戳記的資料來源，會將資料當成由 Adobe 伺服器所收集的點擊來處理。亦即，資料會直接插入訪客歷程中。

該使用 **[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(原稱為 Genesis)**的情況：

* 當您與已建立支援Adobe Analytics連線的第三方供應商接洽時。 資料連接器通常會定期將摘要層級資料永久且自動地整合到Adobe Analytics中。

該使用 **[Data Insertion API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**的情況：

* 當您必須將資料上傳到 Adobe Analytics，且無法使用 Adobe AppMeasurement 或行動 SDK 程式碼時。

該使用&#x200B;**[「客戶屬性」](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**的情況：

* 如果您在客戶關係管理(CRM)資料庫中擷取企業客戶資料，並想要將資料上傳至Experience Cloud。
* 如果您想要在Analytics中使用CRM資料進行更深入的分析，或在Adobe Target中用作定位標準。

該使用 **[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**的情況：

* 如果您想要將Adobe Audience Manager(AAM)受眾資料，例如人口統計資訊（例如性別或收入等級）、心理變數資訊（例如興趣和嗜好）、CRM資料或廣告曝光資料，併入任何Analytics工作流程。
* 如果您希望上傳的CRM資料以時間為基礎，因為此整合會透過點擊傳送新資訊給Analytics點擊。

## 從Adobe Analytics匯出資料 {#section_901C06ABF2014E92B2952906723DF235}

該使用 **[Report Builder](/help/analyze/report-builder/home.md)**的情況：

* 如果工作區的自訂版面選項有限（在Excel的限制內，Report Builder中可能提供任何功能）。
* 將使用者輸入或離線資料來源（印象、成本）大致關聯至Adobe資料。 更永久的資料系結解決方案是Data Sources（請參閱將資料匯入Analytics）。
* 要合併來自不同維度報表的資料（例如，促銷印象報表與促銷點按轉換報表連結）。
* 適用於跨報表套裝檢視。
* 如果需要透過排程進行自動化(XLSX、XLSM、CSV、PDF、TXT、XML、MHT)。

該使用 **[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**的情況：

* 若要存取隱藏在其他 UI 中的變數 (IP 位址、Experience Cloud ID、Analytics 訪客 ID、頁面 URL)
* 若要存取比UI（非標準化表格檢視）更精細的資料
* 以適合樞紐表輸入的格式下載資料
* 如果客戶想要將Adobe資料輸入到協力廠商資料視覺化工具中（略作總結，而非點擊層級）
* 若要在 Adobe Analytics 遇上「低流量」狀態時存取所有不重複維度值

**[Analytics 資料摘要](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**的使用時機：

* 若要運用我們可提供的最詳細資料饋送（訪客ID、點擊）。
* 如果用戶端想要將Adobe資料儲存在用戶端資料庫中，我們可以傳送最精細的資料。
* 如果客戶想要開發商業智慧(BI)工具，或將點擊層級的Adobe資料輸入至協力廠商工具。

當其他視覺化選項都不符合您的需求時，才應該使用&#x200B;**[「報告 API」](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**。有 3 種 API 選項，包括：

* **完整處理**：想要功能豐富的資料 (包括造訪次數、訪客、區段) 時。這是典型的Analytics UI摘要資料，可在約30-90分鐘內取得。 可透過報告建立工具使用。
* **即時**：只想要檢視數個量度和維度，而不希望延遲超過數秒時。這是有限的、經過部分處理的摘要資料，可在約30秒內使用。 包含最受歡迎、獲益者和損失者的獨特演算法。 可透過報告建立工具使用。
* **[!UICONTROL Live Stream]**:當您想要在收集後數秒內取得部分處理的點擊層級Analytics資料串流時。 這是部分處理的資料，可在約30秒內取得。 僅適用於Analytics Premium。 需要某種方式來直觀呈現資料，通常是透過工程服務參與。

## 自訂解決方案 {#section_4A212F26A15947599DFB0399A0440CB6}

該使用工程技術服務的情況:

* 其他的 Adobe 工具都不符合您的需求時。
* 您需要自訂體驗。
* 您需要完全自動化的解決方案。
* 您想要觸及許多裝置。
* 您有多個資料來源。
* 您有複雜的資料ETL（擷取——轉換——載入）需求。
* 您想要自訂品牌。
* 你想要視覺化 [!UICONTROL Analytics Live Stream]。

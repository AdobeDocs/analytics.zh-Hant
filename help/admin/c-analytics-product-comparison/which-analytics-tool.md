---
description: 此說明頁面包含建議使用每種 Adobe Analytics 工具的情況。請依照所列出的順序，來考慮該使用哪種工具。若某項工具不符合需求，請依序考慮清單上的下一種工具。
title: 我該使用哪種 Adobe Analytics 工具呢？
uuid: 1179e49d-3cfc-4abd-a8eb-35c5ae380c16
translation-type: ht
source-git-commit: b4e17f7aad73af250c89cb8117f741f7eed89b7e

---


# 我該使用哪種 Adobe Analytics 工具呢？

此說明頁面包含建議使用每種 Adobe Analytics 工具的情況。請依照所列出的順序，來考慮該使用哪種工具。若某項工具不符合需求，請依序考慮清單上的下一種工具。

如需 Adobe Analytics 產品比較的相關資訊，請前往[此處](/help/admin/c-analytics-product-comparison/analytics-product-comparison.md)取得。

## Adobe Analytics 報告使用者介面 {#section_8265460EBB47405AB19A3B2B0729C8A4}

**[Analysis Workspace](/help/analyze/analysis-workspace/analysis-workspace-features.md)**應該是滿足您所有報告和分析需求的首選使用者介面。Adobe 繼續投資該產品並發行每月更新。如果在 Analysis Workspace 中有無法執行的任務，請考慮以下其他介面。**

該使用 **[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**的情況：

* 入門使用者需要存取預先建立的報告以便導覽。
* 用於瞭解目標活動 (目標分析/A4T) 提升度和可信度。
* 用於存取 UI 中的即時資料。
* 用於設定日曆事件。
* 用於設定目標。
* 用於檢視 Bot 報告。
* 用於在單一 UI 控制面板中查看多個報表套裝。
* 用於存取同時觀看者的獨特影片視覺效果、影片播出時段，以及觀看者下降人數。
* 用於利用排程報告中的「發佈清單」。

該使用 **[Mobile Services UI](https://docs.adobe.com/content/help/zh-Hant/mobile-services/using/home.html)**的情況：

* 若需要「行動應用」資料的獨立檢視.
* 若要管理您行動應用程式 SDK 的實作。
* 若要設定行動裝置廣告，例如應用程式內傳訊、推送訊息及位置目標。
* 若希望應用程式資料的視覺化能夠更有互動性 (Sunburst).
* 若要視覺化地圖上的興趣點。
* 用於期限值量度.

該使用 **[Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md)**的情況：

* 用於匯出 50,000 列的資料
* 若希望以標籤來組織專案工作。
* 使用「網站分析」報表 (3D 路徑報表) 時

該使用 **[Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html)**的情況：

* 當作最具彈性的 Analytics 工具選項使用 (可細分到訪客層級、點擊層級的分析)。
* 用於從 CRM 到 POS 到 Web，建立線上和離線互動的多頻道資料集。
* 用於 (基於規則和演算法模型的) 進階屬性。
* 用於預測性的統計模型 (傾向評分、叢集、關聯性)。
* 用於延遲分析 (事件發生前/後的時間).
* 用於識別並匯出整個 Adobe Experience Cloud 的複雜區段。

## 將資料匯入 Adobe Analytics 中 {#section_B42B998D6E3E4357B024AEFA4EC69A23}

該使用&#x200B;**[「分類」](/help/components/c-classifications2/c-classifications.md)**的情況：

* 有您想要建立關聯以收集值的中繼資料 (eVar、prop、行銷通路) 時
* 選項：

   * 規則產生器：您已針對變數，收集可預測的格式化值 (例如，具有分隔符號的值) 時使用。此方法讓您只要設立規則一次，便可大致上「設定完成、高枕無憂」。
   * 瀏覽器匯入器：如果您沒有可預測的值，或您有需要執行一次性更新的有限值清單，請使用此工具。此方法需要您不斷監控新值的分類。

該使用「**[資料來源](/help/import/c-data-sources/datasrc-home.md)**」的情況：

* 有您想要永久寫入 Adobe Analytics 中的離線資料時
* 選項：

   * 摘要：輕鬆上傳資料，按日期或有限的維度
   * 交易 ID：上傳會將線上端點連線到離線資料的資料，並將匯入的資料完全關聯到線上擷取的訪客快照 (例如，線上完成訂單，然後離線辦理退款)
   * 完整處理：具有時間戳記的資料來源，會將資料當成由 Adobe 伺服器所收集的點擊來處理。也就是，資料會直接插入訪客的日常動向中。

該使用 **[Data Connectors](https://www.adobeexchange.com/experiencecloud.html)(原稱為 Genesis)**的情況：

* 當您與第三方提供者進行交流，而對方已建立 Adobe Analytics 的支援連線時。Data Connectors 通常會定期地自動將摘要層級資料永久納入 Adobe Analytics。

該使用 **[Data Insertion API](https://marketing.adobe.com/developer/documentation/data-insertion/c-data-insertion-api)**的情況：

* 當您必須將資料上傳到 Adobe Analytics，且無法使用 Adobe AppMeasurement 或行動 SDK 程式碼時。

該使用&#x200B;**[「客戶屬性」](/help/components/c-variables/dimensionslist/reports-customer-attributes.md)**的情況：

* 如果您在客戶關係管理 (CRM) 資料庫中擷取企業客戶資料，並且想要將該資料上傳至 Experience Cloud 時。
* 如果您想要使用 CRM 資料在 Analytics 中進行較為深入的分析時，或是將 CRM 資料作為 Adobe Target 中的目標準則時。

該使用 **[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)**的情況：

* 如果您想要納入 Adobe Audience Manager (AAM) 對象資料，如人口資訊 (例如性別或收入等級)、心理變數資訊 (例如興趣及嗜好)、CRM 資料或廣告曝光資料時。
* 如果您想要根據時間上傳 CRM 資料時 (因為此整合會以逐次點擊的方式將新資訊傳送至 Analytics)。

## 從 Adobe Analytics 中匯出資料 {#section_901C06ABF2014E92B2952906723DF235}

該使用 **[Report Builder](/help/analyze/report-builder/home.md)**的情況：

* 若自訂的 Workspace 佈局選項受限時 (在「Report Builder」中，可進行任何操作，只要沒有超過 Excel 的限制即可)。
* 用於將使用者輸入或離線資料來源，鬆散地與 Adobe 資料聯繫起來。希望有更加永久的解決方案，能將資料與資料來源聯繫起來時 (請參閱〈將資料匯入 Adobe Analytics 中〉)。
* 用於合併來自不同維度報表的資料 (例如，將促銷印象報表與促銷一鍵轉換報表合併).
* 用於跨報表套裝的檢視.
* 若希望透過排程來自動化 (XLSX、XLSM、CSV、PDF、TXT、XML、MHT).

該使用 **[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)**的情況：

* 若要存取隱藏在其他 UI 中的變數 (IP 位址、Experience Cloud ID、Analytics 訪客 ID、頁面 URL)
* 若要存取比 UI 更加精細的資料 (非正常的表格檢視)
* 用若要以樞紐分析表輸入所適用的格式下載資料
* 若客戶想要將 (稍微摘要過，而不是點擊層級的) Adobe 資料，輸入到第三方資料視覺化工具中時
* 若要在 Adobe Analytics 遇上「低流量」狀態時存取所有不重複維度值

**[Analytics 資料摘要](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**的使用時機：

* 要利用我們所能提供最精細的資料摘要 (訪客 ID、點擊數) 時。
* 若客戶希望 Adobe 資料能以我們所能傳送最精細的層級，存放在客戶端的資料庫中時.
* 客戶希望開發商務智慧 (BI) 工具，或將點擊層級的 Adobe 資料輸入到第三方工具中時。

當其他視覺化選項都不符合您的需求時，才應該使用&#x200B;**[「報告 API」](https://marketing.adobe.com/developer/get-started/introduction/c-introduction)**。有 3 種 API 選項，包括：

* **完整處理**：想要功能豐富的資料 (包括造訪次數、訪客、區段) 時。這是典型的 Analytics UI 摘要資料，需要約 30-90 分鐘才可供使用。可以透過「Report Builder」來使用。
* **即時**：只想要檢視數個量度和維度，而不希望延遲超過數秒時。這是有限而只經過部分處理的摘要資料，只要約 30 秒以內就可供使用。包括獨特的演算法，可針對「最受歡迎」、「獲益者」和「損失者」。可以透過「Report Builder」來使用。
* **[!UICONTROL 即時資料流]**：想要經過部分處理的點擊層級 Analytics 資料，而希望收集時間只花費數秒時。這是經過部分處理的資料，只要約 30 秒以內就可供使用。只有 Analytics Premium 才提供此 API。需要某種方法才能視覺化資料，通常會涉及工程技術服務。

## 自訂解決方案 {#section_4A212F26A15947599DFB0399A0440CB6}

該使用工程技術服務的情況：

* 其他的 Adobe 工具都不符合您的需求時。
* 想要自訂體驗時。
* 想要完整的自動化解決方案時。
* 想要觸及許多裝置時。
* 具有多個資料來源時。
* 具有複雜的資料 ETL (擷取、轉換、載入) 需求時。
* 想要自訂品牌時。
* 想要視覺化 [!UICONTROL Analytics Live Stream] 時。

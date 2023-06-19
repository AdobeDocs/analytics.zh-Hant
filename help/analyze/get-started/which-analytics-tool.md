---
description: 此說明頁面包含建議使用每種 Adobe Analytics 工具的情況。請依照所列出的順序，來考慮該使用哪種工具。若某項工具不符合需求，請依序考慮清單上的下一種工具。
title: 我該使用哪種 Adobe Analytics 工具呢？
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
source-git-commit: a288253816fa73444dd5078d56d3d30e92aebe3f
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 96%

---

# 我該使用哪種 Adobe Analytics 工具呢？

此說明頁面包含建議使用每種 Adobe Analytics 工具的情況。請依照所列出的順序，來考慮該使用哪種工具。若某項工具不符合需求，請依序考慮清單上的下一種工具。

若要了解更多關於 Adobe Analytics 產品比較，請參閱 [Analytics 產品比較](/help/analyze/get-started/analytics-product-comparison.md)。

以下是有關比較各種 Adobe Analytics 工具的影片：

>[!VIDEO](https://video.tv.adobe.com/v/27220/?quality=12)

## Adobe Analytics 報告使用者介面 {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** 應該是滿足您所有報告和分析需求的首選使用者介面。Adobe 繼續投資該產品並發行每月更新。如果在 Analysis Workspace 中有無法執行的任務，請考慮以下其他介面。**

該使用 **[Reports &amp; Analytics](/help/analyze/reports-analytics/overview/report-overview.md)**&#x200B;的情況：

* 入門使用者需要存取預先建立的報告以便導覽。
* 用於存取 UI 中的即時資料。
* 用於設定日曆事件。
* 用於設定目標。
* 用於檢視 Bot 報告。
* 用於取用不重複影片的「影片時段」與「觀賞人數減退」等資料的視覺化。

該使用 **[Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html)** 的情況：

* 當作最具彈性的 Analytics 工具選項使用 (可細分到訪客層級、點擊層級的分析)。
* 用於從 CRM 到 POS 到 Web，建立線上和離線互動的多頻道資料集。
* 用於 (基於規則和演算法模型的) 進階屬性。
* 用於預測性的統計模型 (傾向評分、叢集、關聯性)。
* 用於延遲分析 (事件發生前/後的時間).
* 用於識別並匯出整個 Adobe Experience Cloud 的複雜區段。

## 將資料匯入 Adobe Analytics 中  {#import}

該使用&#x200B;**[「分類」](/help/components/classifications/c-classifications.md)**&#x200B;的情況：

* 有您想要建立關聯以收集值的中繼資料 (eVar、prop、行銷通路) 時
* 選項：

   * 規則產生器：您已針對變數，收集可預測的格式化值 (例如，具有分隔符號的值) 時使用。此方法讓您只要設立規則一次，便可大致上「設定完成、高枕無憂」。
   * 瀏覽器匯入器：如果您沒有可預測的值，或您有需要執行一次性更新的有限值清單，請使用此工具。此方法需要您不斷監控新值的分類。

該使用「**[資料來源](/help/import/data-sources/overview.md)**」的情況：

* 有您想要永久寫入 Adobe Analytics 中的離線資料時
* 選項：

   * 摘要：輕鬆上傳資料，按日期或有限的維度
   * 交易 ID：上傳會將線上端點連線到離線資料的資料，並將匯入的資料完全關聯到線上擷取的訪客快照 (例如，線上完成訂單，然後離線辦理退款)
   * 完整處理：具有時間戳記的資料來源，會將資料當成由 Adobe 伺服器所收集的點擊來處理。也就是，資料會直接插入訪客的日常動向中。

應該使用 **[Adobe Exchange 整合](https://www.adobeexchange.com/experiencecloud.html)**：

* 當您與協力廠商提供者進行交流，而對方已建立與 Adobe Analytics 的支援連線時。 整合應用程式通常會定期地自動將摘要層級資料永久納入 Adobe Analytics。

**[Data Insertion API](/help/import/c-data-insertion-api/c-data-insertion-api.md)** 使用時機：

* 當您必須將資料上傳到 Adobe Analytics，且無法使用 Adobe AppMeasurement 或行動 SDK 程式碼時。

**[大量資料插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* 「資料插入 API」和「大量資料插入 API」都是將伺服器端的蒐集資料送至 Adobe Analytics 的方法。每發生一個事件時，「資料插入 API」都會被呼叫。「大量資料插入 API」接受含有事件資料的 CSV 格式檔案 (其中每一行儲存一個事件)。 若您正在實施新的伺服器端蒐集作業，建議採用「大量資料插入 API」。

**[「客戶屬性」](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html)**&#x200B;使用時機：

* 如果您在客戶關係管理 (CRM) 資料庫中擷取企業客戶資料，並且想要將該資料上傳至 Experience Cloud 時。
* 如果您想要使用 CRM 資料在 Analytics 中進行較為深入的分析時，或是將 CRM 資料作為 Adobe Target 中的目標準則時。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** 使用時機：

* 如果您想要將Adobe Audience Manager對象資料，例如人口資訊（例如性別或收入等級）、心理變數資訊（例如興趣和愛好）、CRM資料或廣告曝光資料整合到任何Analytics工作流程中。
* 如果您想要根據時間上傳 CRM 資料時 (因為此整合會以逐次點擊的方式將新資訊傳送至 Analytics)。

## 從 Adobe Analytics 中匯出資料  {#export}

**[Report Builder](/help/analyze/report-builder/home.md)** 使用時機：

* 若自訂的 Workspace 配置選項受限時 (在「Report Builder」中，可進行任何操作，只要沒有超過 Excel 的限制即可)。
* 用於將使用者輸入或離線資料來源，鬆散地與 Adobe 資料聯繫起來。希望有更加永久的解決方案，能將資料與資料來源聯繫起來時 (請參閱〈將資料匯入 Adobe Analytics 中〉)。
* 用於合併來自不同維度報表的資料 (例如，將促銷印象報表與促銷一鍵轉換報表合併).
* 若要合併不同報表套裝的資料，可在同一表格中併排匯總或顯示。
* 若希望透過排程來自動化 (XLSX、XLSM、CSV、PDF、TXT、XML、MHT)。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** 使用時機：

* 若要存取隱藏在其他 UI 中的變數 (IP 位址、Experience Cloud ID、Analytics 訪客 ID、頁面 URL)
* 若要存取比 UI 更加精細的資料 (非正常的表格檢視)
* 用若要以樞紐分析表輸入所適用的格式下載資料
* 若客戶想要將 (稍微摘要過，而不是點擊層級的) Adobe 資料，輸入到協力廠商資料視覺化工具中時
* 若要在 Adobe Analytics 遇上「低流量」狀態時存取所有不重複維度項目

**[Analytics 資料摘要](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**&#x200B;使用時機：

* 要利用我們所能提供最精細的資料摘要 (訪客 ID、點擊數) 時。
* 若客戶希望 Adobe 資料能以我們所能傳送最精細的層級，存放在客戶端的資料庫中時.
* 客戶希望開發商務智慧 (BI) 工具，或將點擊層級的 Adobe 資料輸入到協力廠商工具中時。

當其他視覺化選項都不符合您的需求時，才應該使用&#x200B;**[「報告 API」](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)**。有 3 種 API 選項，包括：

* **完整處理**：想要功能豐富的資料 (包括造訪次數、訪客、區段) 時。這是典型的 Analytics UI 摘要資料，需要約 30-90 分鐘才可供使用。可以透過「Report Builder」來使用。
* **即時**：只想要檢視數個量度和維度，而不希望延遲超過數秒時。這是有限而只經過部分處理的摘要資料，只要約 30 秒以內就可供使用。包括獨特的演算法，可針對「最受歡迎」、「獲益者」和「損失者」。可以透過「Report Builder」來使用。
* **[!UICONTROL 即時資料流]**：想要經過部分處理的點擊層級 Analytics 資料，而希望收集時間只花費數秒時。這是經過部分處理的資料，只要約 30 秒以內就可供使用。只有 Analytics Premium 才提供此 API。需要某種方法才能視覺化資料，通常會涉及工程技術服務。

## 自訂解決方案 {#custom-solutions}

工程技術服務使用時機：

* 其他的 Adobe 工具都不符合您的需求時。
* 想要自訂體驗時。
* 想要完整的自動化解決方案時。
* 想要觸及許多裝置時。
* 具有多個資料來源時。
* 具有複雜的資料 ETL (擷取、轉換、載入) 需求時。
* 想要自訂品牌時。
* 想要視覺化 [!UICONTROL Analytics Live Stream] 時。

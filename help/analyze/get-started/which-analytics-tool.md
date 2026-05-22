---
description: 此說明頁面包含每個Adobe Analytics工具的建議使用案例。 工具應按照列出的順序來考慮。 如果某個工具不符合需求，請移至下一個工具以供考慮。
title: 我該使用哪種 Adobe Analytics 工具呢？
feature: Analytics Basics
exl-id: d65575df-19c6-4129-89c8-d36de7bb6b2f
TQID: https://experienceleague.adobe.com/xk485fKU7Q2DeZIYaTtN-a4JKnyVamAygW03z7ffAOk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1175
ht-degree: 73%

---

# 我該使用哪種 Adobe Analytics 工具呢？

此說明頁面包含每個Adobe Analytics工具的建議使用案例。 工具應按照列出的順序來考慮。 如果某個工具不符合需求，請移至下一個工具以供考慮。

若要了解更多關於 Adobe Analytics 產品比較，請參閱 [Analytics 產品比較](/help/analyze/get-started/analytics-product-comparison.md)。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [工具比較](https://video.tv.adobe.com/v/27220?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


## Adobe Analytics 報告使用者介面 {#user-interfaces}

**[Analysis Workspace](/help/analyze/analysis-workspace/home.md)** 應該是滿足您所有報告和分析需求的首選使用者介面。 Adobe 繼續投資該產品並發行每月更新。 如果在 Analysis Workspace 中有無法執行的任務，請考慮以下其他介面。**

**[Adobe Analytics 儀表板](/help/analyze/mobile-app/home.md)**&#x200B;允許使用者透過行動裝置存取直覺易用的計分卡。 計分卡是關鍵量度和其他元件的集合，以圖磚式版面配置呈現，點選上面的項目即可取得詳細劃分資料和趨勢報表。 iOS 和 Android 作業系統均支援行動應用程式。

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** 是適用於 Microsoft Excel 的增益集，可在 Mac、Windows 和網頁瀏覽器上執行。 這可讓您根據能插入 Excel 工作表中的 Adobe Analytics 資料來建立自訂請求。 這些請求可動態參考工作表中的儲存格，而您可以更新及自訂 Report Builder 展示資料的方式。

**[舊版 Report Builder](/help/analyze/legacy-report-builder/home.md)** 是適用於 Microsoft Excel 的增益集，僅可在 Windows 上執行。 這可讓您根據能插入 Excel 工作表中的 Adobe Analytics 資料來建立自訂請求。 這些請求可動態參考工作表中的儲存格，而您可以更新及自訂 Report Builder 展示資料的方式。

**[Activity Map](/help/analyze/activity-map/overview.md)** 是 Adobe Analytics 中的一項功能，可提供網頁和行動應用程式上使用者參與度的視覺化表示。 此功能可讓行銷人員和分析師追蹤和分析使用者的互動情形，例如點擊、暫留和捲動行為。

## 將資料匯入 Adobe Analytics 中 {#import}

**[分類](/help/components/classifications/classifications-overview.md)**&#x200B;適用於以下情形：

* 您想要與中繼資料建立關聯以便收集值 (eVar、prop、行銷管道) 的時候。 Adobe 建議使用[分類集](/help/components/classifications/sets/overview.md)。 分類規則產生器和分類匯入工具是將分類資料導入 Adobe Analytics 的舊方法。

**[資料來源](/help/import/data-sources/overview.md)**&#x200B;使用時機：

* 有您想要永久寫入 Adobe Analytics 中的離線資料時
* 選項：
   * 摘要：輕鬆上傳資料，按日期或有限的維度
   * 交易 ID：上傳會將線上端點連線到離線資料的資料，並將匯入的資料完全關聯到線上擷取的訪客快照 (例如，線上完成訂單，然後離線辦理退款)

**[Adobe Exchange 整合](https://www.adobeexchange.com/experiencecloud.html)**&#x200B;使用時機：

* 當您與協力廠商提供者進行交流，而對方已建立與 Adobe Analytics 的支援連線時。 整合應用程式通常會定期地自動將摘要層級資料永久納入 Adobe Analytics。

**[大量資料插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)**

* 「大量資料插入 API」接受含有事件資料的 CSV 格式檔案，其中每一行儲存一個事件。 Adobe 建議，任何需要伺服器端程式碼或因其他原因無法使用 AppMeasurement 或 Web SDK 進行資料收集的實作使用大量插入 API。

**[資料插入 API (舊版)](/help/import/c-data-insertion-api/c-data-insertion-api.md)** 適用於以下情形：

* 當您需要將資料導入 Adobe Analytics 且無法使用 AppMeasurement、Web SDK 或大量資料插入 API 時。

「**[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=zh-Hant)**」應在以下情況時使用：

* 如果您在客戶關係管理(CRM)資料庫中擷取企業客戶資料，且想要將該資料上傳至CX Enterprise。
* 如果您想要使用CRM資料在Analytics中進行更深入的分析，或在Adobe Target中作為鎖定目標條件。

**[Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md)** 使用時機：

* 如果您想要將 Adobe Audience Manager 對象資料，例如人口資訊 (例如性別或收入等級)、心理變數資訊 (例如興趣及嗜好)、CRM 資料或廣告曝光數資料納入任何 Analytics 工作流程。
* 如果您希望上傳的CRM資料以時間為基礎，因為這項整合會依點選將新資訊傳送至Analytics。

## 從 Adobe Analytics 中匯出資料 {#export}

**[Report Builder](/help/analyze/report-builder/rb-overview.md)** 使用時機：

* 若自訂的 Workspace 配置選項受限時 (在「Report Builder」中，可進行任何操作，只要沒有超過 Excel 的限制即可)。
* 用於將使用者輸入內容或離線資料來源 (印象、費用) 與 Adobe 資料鬆散連結。 連結資料更加持久的解決方案是資料來源 (請參閱〈將資料匯入 Analytics〉)。
* 用於合併來自不同維度報告的資料 (例如，將促銷印象報告與促銷一鍵轉換報告合併).
* 若要合併不同報告套裝的資料，可在同一表格中併排匯總或顯示。
* 若希望透過排程來自動化 (XLSX、XLSM、CSV、PDF、TXT、XML、MHT)。

**[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)** 使用時機：

* 若要存取隱藏在其他 UI 中的變數 (IP 位址、Experience Cloud ID、Analytics 訪客 ID、頁面 URL)
* 存取比UI更精細的資料（非標準化表格檢視）
* 若要以適合樞紐分析表輸入的格式下載資料
* 若客戶想要將 (稍微摘要過，而不是點擊層級的) Adobe 資料，輸入到協力廠商資料視覺化工具中時
* 若要在 Adobe Analytics 遇上「低流量」狀態時存取所有不重複維度項目

**[Analytics 資料摘要](/help/export/analytics-data-feed/c-df-contents/datafeeds-contents.md)**&#x200B;使用時機：

* 運用我們能夠提供的最精細資料摘要（訪客ID、點選）。
* 如果使用者端希望將Adobe資料儲存在使用者端資料庫中，我們可以以最精細的層級傳送。
* 客戶希望開發商務智慧 (BI) 工具，或將點擊層級的 Adobe 資料輸入到協力廠商工具中時。

當其他視覺化選項都不符合您的需求時，才應該使用&#x200B;**[「報告 API」](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-guide.md)**。 有 3 種 API 選項，包括：

* **完整處理**：想要功能豐富的資料 (包括造訪次數、訪客、區段) 時。 這是典型的Analytics UI摘要資料，大約30到90分鐘內即可使用。 可透過Report Builder使用。
* **即時**：只想要檢視數個量度和維度，而不希望延遲超過數秒時。 這是有限、部分處理的摘要資料，可在約30秒內使用。 包括最熱門、獲益者和損失者的獨特演演算法。 可透過Report Builder使用。
* **[!UICONTROL 即時資料流]**：想要經過部分處理的點擊層級 Analytics 資料，而希望收集時間只花費數秒時。 這是部分處理的資料，可在約30秒內使用。 僅適用於Analytics Premium。 需要一些視覺化資料的方式，通常透過工程技術服務參與的方式。

## 自訂解決方案 {#custom-solutions}

工程技術服務使用時機：

* 其他的 Adobe 工具都不符合您的需求時。
* 您想要自訂體驗。
* 您想要完全自動化的解決方案。
* 您想要連線到許多裝置。
* 您有多個資料來源。
* 您有複雜的資料ETL (Extract-Transform-Load)需求。
* 您想要自訂品牌。
* 您想要視覺化[!UICONTROL Analytics即時資料流]。

---
description: 本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。
seo-description: 本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。
seo-title: Adobe Analytics-關鍵概念
title: Adobe Analytics-關鍵概念
uuid: ef5701c5-2d3e-4847-851f-9312d55db1a8
translation-type: tm+mt
source-git-commit: d3819975bb65ccf345d60474e268ed9d1b1606a7

---


# Adobe Analytics-關鍵概念

本節包含 Adobe Analytics 的重要概念、概念的簡短說明，以及主題其他詳細資訊的特定文件連結。

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| 產品 | 說明 | 文件連結 |
|--- |--- |--- |
| Analysis Workspace | 建立強穩、自訂分析專案的瀏覽器解決方案，讓您獲得更多見解。提供比報告與分析更多的報告彈性 | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Report &amp; Analytics (前稱為 SiteCatalyst) | 報告與分析的瀏覽器解決方案。Analytics 套裝中的入門工具。 | [報告與分析首頁](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | 可讓您從Adobe Analytics資料建立自訂請求，並使用Microsoft Excel視覺化它們的Excel增益集。 | [報告建立工具首頁](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Ad Hoc Analysis (前稱為 Discover) | 進階數位分析的Java工具。在2014年第三季結束生命週期。 | [臨機分析首頁](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Data Workbench (前稱為 Insight) | 專門設計來收集、處理、分析以及呈現多個管道的線上和離線客戶互動情形。 | [資料工作台用戶端](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | 用於儲存和自訂報表的原始、未處理資料複本，可供您透過篩選資料的方式來執行。非點擊層級。 | [資料倉庫首頁](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | 將整個 Adobe Experience Cloud 上行動應用程式的行動行銷功能集合在一起，讓您瞭解並改進使用者與應用程式的互動。 | [Mobile Services首頁](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Adobe Exchange Data Connectors(之前稱為Genesis) | 從第三方應用程式匯入追蹤資料至Analytics，在一個中央位置提供端對端的效能可見度。 | [資料連接器首頁](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| 動態標籤管理 (DTM) | 可讓您管理所有網站上的分析、目標及其他標籤，不受網域數目影響。 | [DTM首頁](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | Adobe的新一代網站標籤和行動SDK管理功能。 | [Adobe Launch首頁](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Key terminology {#concept_E473ACBB8E4A42B4AC005538AC12F154}

按一下[此處](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html)可存取 Adobe Analytics 術語的擴充詞彙表。

| 詞語 | 說明 | 文件連結 |
|--- |--- |--- |
| Prop(自訂流量) | 用來追蹤逐頁網站流量活動的維度。Prop 無法在頁面間持續存在。流量變數的主要應用範圍: <ul><li>輕鬆計算出「最受歡迎」的特定值</li><li>瞭解使用者如何瀏覽您的網站 </li></ul><br>流量變數範例：頁面名稱、網站區域、瀏覽器</br> | [Prop](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar(自訂轉換) | 持續存在於您自訂期間的維度。有效期選項包括事件有效期、瀏覽有效期或 X 天有效期，且應由該變數上執行的分析類型來驅動。<br>eVar和prop之間的主要差異：</br><ul><li>Prop通常用於路徑分析，因為持續性被移除。</li><li>eVar通常用於轉換分析。</li></ul><br>轉換變數範例：內部搜尋詞、內部促銷、外部促銷活動(s. campaign)</br> | [eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| 事件/度量(s. events) | 測量我們希望訪客在網站上採取的關鍵動作的度量。有 3 種事件類型: 計數器、數值和貨幣。事件新增至轉換變數 (eVar) 報表時最為有用。eVar 可提供關於所發生情形的質化資訊，事件則可提供關於所發生情形的量化資訊。<br>eVar與事件之間的主要差異：</br><ul><li>eVar會告訴我們哪些人、哪些人，或是哪些影響了轉換</li><li>事件測量發生了多少轉換</li></ul><br>轉換事件範例: 訂購、應用程式啟動、銷售機會、收入。</br> | [事件](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| 元件 | 您可以拖放至專案的維度、量度、區段和時間粒度(日期範圍)。 | [元件](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| 維度 | eVar、prop、分類和標準Adobe收集到的值集合。 | [維度](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| 量度 | 實作事件和計算量度的集合。 | [量度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| 計算量度 | 能夠從實施中擷取的現有量度衍生自訂度量。 | [計算量度](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| 區段 | 能夠建立、管理、共用並套用功能強大且目標專一的對象區段至 Analytics 報表。區段會在 Analytics 產品間共用，也能在 Experience Cloud 間共用。 | [區段](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| 時間(日期範圍) | 篩選日期至任何時段，並建立可在分析中重復使用的自訂日期範圍。 | [日期範圍](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| 視覺效果 | 豐富的視覺效果，可協助您將資料帶入專案中。 | [視覺化](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| 組織 | 可限制專案或虛擬報表套裝中可存取的元件。 | [VRS教學專案](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[比較](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Key features {#concept_216E78AD39DD453D940AE857F4C7D4DF}

<table id="table_5CD38BD3BE854E69B6925EA3F02AFC92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 報告 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 文件連結 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 完整報表清單 </td> 
   <td colname="col2"> Adobe Analytics 中所有可用報表的定義。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自訂流量 (Prop) </td> 
   <td colname="col2">用於追蹤逐頁網站流量活動。Prop 無法在頁面間持續存在。流量變數的主要應用範圍: 
    <ul id="ul_A935EC5271684B9599F683C7B31400ED"> 
     <li id="li_58E0596050A34ACC821916EA61E946EF">擷取與頁面檢視、瀏覽、訪客或例項關聯的值。 </li> 
     <li id="li_2B4C557AAD0544BE8204C0D7CE587175">尋找「最受歡迎的」特定值。 </li> 
     <li id="li_7FA62BE657F047459DF439BFB9F332F5">查看使用者前來您網站的路徑。 </li> 
    </ul> <p>流量變數的範例: 頁面名稱、網站區域、瀏覽器。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自訂轉換 (eVar) </td> 
   <td colname="col2">主要用於報告轉換事件，您可以自訂其持續期間。有效期選項包括事件有效期、瀏覽有效期或 X 天有效期，且應由該變數上執行的分析類型來驅動。 <p>轉換變數和流量變數之間的重要差異: </p> 
    <ul id="ul_B0A7482A81B94C5F86C06E5507DB393D"> 
     <li id="li_272E414520AA4603AE5EC397B0F93630"> 自訂流量變數關聯至流量量度，而非轉換。通常用於路徑分析。 </li> 
     <li id="li_EBBF9A35C64845FE9683540DFA89E7E9">自訂轉換變數可以關聯至流量和轉換，通常用於轉換分析。 </li> 
    </ul> <p>轉換變數範例: 內部搜尋詞、內部促銷、外部促銷活動 (s.campaign)。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 成功事件 (s.events) </td> 
   <td colname="col2"> <p>測量我們希望訪客在網站上採取的關鍵動作。 </p> <p>有 3 種事件類型: 計數器、數值和貨幣。事件新增至轉換變數 (eVar) 報表時最為有用。eVar 可提供關於所發生情形的質化資訊，事件則可提供關於所發生情形的量化資訊。 </p> <p>轉換變數和自訂事件之間的重要差異: </p> 
    <ul id="ul_2B95D7437DE444DD9618DBFE6A8612D1"> 
     <li id="li_5951858853334EFA931A5BC57E5C933F">轉換變數可提供影響轉換的人、事、物資訊。 </li> 
     <li id="li_339755C842714E0DB8DB4DFAA43AB4F7"> 自訂事件用於測量發生了多少轉換。 </li> 
    </ul> <p>轉換事件範例: 訂購、應用程式啟動、銷售機會、收入。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/success_event.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/success_event.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 網站量度 </td> 
   <td colname="col2"> 顯示您網站的相關量化資訊，例如獨特訪客、訂購、收入等。每個量度都能放在其他項目型報表中。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_metrics.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_site_metrics.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 網站內容 </td> 
   <td colname="col2"> 顯示您網站中最活躍的網頁與區域以及最常用的伺服器。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_site_content.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_site_content.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行動 </td> 
   <td colname="col2"> 顯示從行動裝置或平板電腦存取的網站相關資訊。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_mobile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_mobile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行動應用程式 </td> 
   <td colname="col2"> <p>顯示行動應用程式的相關基本使用資訊。我們的 SDK 一經實施並開啟報告功能後，這些報表就可供使用。 </p> <p>此外，Adobe Mobile Services 已建立單獨的行動應用程式介面，可提供更完整的應用程式資料，讓您了解並改進使用者對您應用程式的互動程度。 </p> <p>介面存取位置: </p> <p><a href="https://mobilemarketing.adobe.com" format="https" scope="external"> https://mobilemarketing.adobe.com</a> </p> </td> 
   <td colname="col3"> <p>Adobe Mobile Services: </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_TW/mobile/</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 路徑報表 </td> 
   <td colname="col2"> 顯示訪客存取您網站網頁之順序的相關資訊。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_paths.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_paths.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 產品 </td> 
   <td colname="col2"> 識別個別產品和產品群組 (類別) 對各種轉換量度 (如收入或結帳) 的貢獻度。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_products.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_products.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客保留率 </td> 
   <td colname="col2"> 顯示客戶忠誠度的相關資訊，例如有多少訪客回訪您的網站以及回訪頻率。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_retention.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_retention.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客資料 </td> 
   <td colname="col2"> 協助您瞭解不同資料類別 (包括國家、州、ZIP/郵遞區號和網域) 之客戶的購買模式。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_profile.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_visitor_profile.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行銷管道 </td> 
   <td colname="col2">這些報表可協助您理解哪些外部管道將使用者引入您的網站，以及在促進轉換方面哪些管道最有效。並提供首次接觸和上次接觸歸因檢視。 <p>這是 Adobe Analytics 慣用的外部流量來源報表 (優先於促銷活動或流量來源)，因為這可同時提供付費和自然管道的最全面資訊。 </p> </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/mchannel/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/mchannel/index.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自訂報表、報表連結、書籤和控制面板 </td> 
   <td colname="col2"> 在 Analytics 介面中儲存和/或與他人共用您的工作的方法。 </td> 
   <td colname="col3">自訂報表: <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/reports_custom.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/reports_custom.html</a> </p> <p>報表連結: </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/t_reports_share_link.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/sc/user/t_reports_share_link.html</a> </p> <p>書籤 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/bookmarks.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/sc/user/bookmarks.html</a> </p> <p>控制面板 </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| 量度名稱 | 定義 | 文件連結 |
|---|---|---|
| 完整量度清單 | Adobe Analytics 中所有量度的定義。 | [https://marketing.adobe.com/resources/help/en_US/reference/metrics.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics.html) |
| 獨特訪客 | 在指定時段內，前往網站的不重複訪客數量。 | [https://marketing.adobe.com/resources/help/en_US/reference/metrics_unique_visitors.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_unique_visitors.html) |
| 瀏覽 | 某一段時間的頁面檢視順序。瀏覽開始於一個人開始檢視網站的某個頁面，結束於閒置 30 分鐘後。 | [https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html) |
| 頁面檢視 | 當訪客檢視您的網站頁面時就會發生頁面檢視。 | [https://marketing.adobe.com/resources/help/en_US/reference/metrics_page_view.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_page_view.html) |
| 例項 | 變數被定義的次數。每一次 Adobe Analytics 查看變數中的值時，該對應報表中的例項就會遞增一。 | [https://marketing.adobe.com/resources/help/en_US/reference/metrics_instance.html](https://marketing.adobe.com/resources/help/en_US/reference/metrics_instance.html) |
| 計算量度 | 您可從現有量度建立的自訂量度。例如，如果您有收入和瀏覽次數，便可建立每次瀏覽平均收入或收入除以瀏覽次數 (收入/瀏覽次數)。 | [https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) |

## 匯入選項 {#concept_7C6DF03B5F9149E2A77F36C739432059}

| 選項 | 說明 | 文件連結 |
|---|---|---|
| 分類匯入工具 | 透過瀏覽器或 FTP 上傳，根據擷取的維度匯入中繼資料。相較於規則產生器，此為手動方式。 | [https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| 規則產生器 | 根據使用者定義規則，自動建立維度的中繼資料分類。 | [https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| 資料來源 | 根據維度或僅依日期匯入離線量度至 Analytics。 | [https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html](https://marketing.adobe.com/resources/help/en_US/sc/datasources/datasrc_home.html) |
| Data Connectors | 請參閱[產品](../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B)。 |  |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}


<table id="table_99867D82082D4756872FC3ABD83A33A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 介面報表下載 </td> 
   <td colname="col2"> 從 Analytics 匯出資料的最簡單方式。 </td> 
   <td colname="col3">https://microsite.omniture.com/t2/help/en_US/survey/index.html#Downloading_a_Report_Using_ <p>Basic_Options </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Warehouse </td> 
   <td colname="col2">請參閱<a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">產品</a>。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Report Builder </td> 
   <td colname="col2">請參閱<a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">產品</a>。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics API </td> 
   <td colname="col2"> 建立對 Analytics 資料的自訂查詢。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/developer/documentation" format="https" scope="external"> https://marketing.adobe.com/developer/documentation</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 點按流資料饋送 </td> 
   <td colname="col2"> 從 Analytics 取得資料的最詳細方式。設定 Analytics 的點擊層級回饋。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/zh_TW/sc/clickstream/datafeeds_reference.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 排程資料 </td> 
   <td colname="col2"> 大部分 Adobe Analytics 匯出選項都提供排程資料和報表傳送至電子郵件或 FTP 站台的功能。 </td> 
   <td colname="col3"> - </td> 
  </tr> 
 </tbody> 
</table>

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

<table id="table_53039DCCAC1D47F7A1E3485609D13E4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 方法/資源 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 文件連結 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 開發人員資源 </td> 
   <td colname="col2"> 概述可用於收集所有可用平台 (網路、行動應用程式、視訊、Flash 等) 之 Analytics 資料之程式庫的文件 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/developer.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 實施指引 </td> 
   <td colname="col2"> 說明資料收集變數，並詳述如何在 JavaScript 中實施資料收集程式碼。 </td> 
   <td colname="col3"> <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> App Measurement (s_code) </td> 
   <td colname="col2"> 全域變數管理 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html#" format="html" scope="external"> https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 應用程式 SDK </td> 
   <td colname="col2"> 可自訂套裝，包含應用程式設定檔的預先填入版本。 </td> 
   <td colname="col3">iOS: <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=requirements" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=requirements</a> </p> <p>Android: </p> <p><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/mobile/android/requirements.html</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Tag Management (DTM) </td> 
   <td colname="col2">請參閱<a href="../../analyze/reports-analytics/key-concepts.md#concept_833EDD4EB056491DA1BC5A3A45FE285B" format="dita" scope="local">產品</a>。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VISTA </td> 
   <td colname="col2"> 從伺服器端填入報表變數的方法。VISTA 採用訪客區段規則來建立所有線上資料的即時區段。這些規則可讓您以幾近隨心所欲的方式對選擇的資料進行變更或區段，而無須在網站上實施複雜的邏輯。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 處理規則 </td> 
   <td colname="col2"> 透過「管理工具」區段簡化資料收集並管理傳送至報表之內容的方法。處理規則可以簡化與 IT 團隊以及網頁開發人員之間的互動，提供介面用於設定、修改和複製變數。 </td> 
   <td colname="col3"><a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 除錯工具選項 </td> 
   <td colname="col2"> 我們提供數個除錯工具和封包 Sniffer，供您驗證實施。我們慣用的除錯工具是 Charles。其他工具包括 Adobe Debugger、HTTPFox、Firebug、Omnibug、Fiddler 和 HTTPWatch。 </td> 
   <td colname="col3">Adobe Debugger: <p><a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html" format="https" scope="external"> https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html</a> </p> <p>Charles: </p> <p><a href="https://www.charlesproxy.com/" format="http" scope="external"> https://www.charlesproxy.com/</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

---
title: Adobe Analytics中使用的詞彙
description: Adobe Analytics詞彙表，定義常用詞語。
translation-type: tm+mt
source-git-commit: aeb2fc9f53aec6b4e53378b87e64c01f0b437d87

---


# Adobe Analytics中使用的詞彙

使用此詞彙表來瞭解Adobe Analytics使用許多術語的上下文。

* **活動圖：** 一種瀏覽器外掛程式，顯示網站上哪些區域最常被點按。請參閱 [分析使用指南中的Activity Map](../analyze/activity-map/activity-map.md) 。
* **管理控制台：** 可以參考：
   * 舊有管理工具，在Adobe Analytics中管理報表套裝設定。在舊版Adobe Analytics中，也管理了使用者權限。請參閱 [管理使用者指南中的管理工具](../admin/admin/c-admin-tools.md) 。
   * Adobe管理主控台，其中提供產品存取權，並管理使用者權限。請參閱 [管理使用者指南中的Admin Console](../admin/admin-console/home.md) 。
* **配置：** 如果轉換變數在瀏覽期間遇到多個值，變數的配置設定會決定保留的值。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **異常：** 偵測使用統計模型自動尋找資料中意外的趨勢。此模型會分析量度並決定上下界限和值的預期範圍。請參閱 [分析使用指南中的異常偵測](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) 。
* **AppMeasurement：** 用來收集資料並傳送給Adobe的程式碼庫。請參閱實施使用者指南 [的首頁](../implement/home.md) 。
* **ASI槽：** 不再存在。在舊版Adobe Analytics中，ASI槽提供臨時報表套裝容器來檢視分段資料。在目前版本的Adobe Analytics中，可以立即套用區段至任何報表。
* **劃分：** 可讓您在其他維度的上下文中檢視維度。請參閱 [分析使用指南中的劃分維度](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) 。
* **反彈：** 包含單一點擊的瀏覽。請參閱 [元件使用指南中的彈回數](../components/c-variables/c-metrics/metrics-bounces.md) 。另請參閱「單次存取」。
* **計算量度：** 允許結合現有量度、統計函數和公式，以便用於報告中。請參閱 [元件使用指南中的計算量度](../components/c-calcmetrics/cm-overview.md) 。
* **促銷活動：** 可以參考：
   * 促銷活動變數，會填入追蹤代碼維度。請參閱 [實施使用者指南中的頁面變數](../implement/js-implementation/c-variables/page-variables.md) 。
   * 追蹤代碼維度的預設分類；自動建立所有報表套裝。
   * Adobe Campaign，屬於Adobe Experience Cloud的一部分。有關 [Adobe.com](https://www.adobe.com/marketing/campaign.html)的更多資訊。
* **頻道：** 可以參考：
   * 頻道變數，會填入「網站區域」維度。請參閱 [實施使用者指南中的頁面變數](../implement/js-implementation/c-variables/page-variables.md) 。
   * 行銷管道是一種元件，可協助瞭解使用者如何到達您的網站。請參閱 [元件使用指南中的行銷管道](../components/c-marketing-channels/c-overview.md) 。
* **分類：** Adobe Analytics中允許分組維度值的功能。請參閱 [元件使用指南中的分類](../components/c-classifications2/c-classifications.md) 。
* **Clickmap：** 不再使用。舊版瀏覽器外掛程式，顯示網站上哪些區域最常被點按。此工具已退役，以支援Activity Map。
* **點按流資料饋送：** 請參閱資料饋送。
* **世代：** 在指定期間分享共同特性的一組人。See [What is Cohort Analysis?](../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) 在分析使用指南中。
* **Collection伺服器：** 請參閱資料收集伺服器。
* **轉換變數：** 稱為eVar。儲存自訂值，並保留變數值，直到其過期為止。See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **關聯：** 不再用作詞語；取代為維度劃分。在舊版Adobe Analytics中，關聯授予了劃分流量變數的能力。請參閱 [分析使用指南中的劃分維度](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) 。
* **目前的資料：** 某些報告中的選項，允許納入最近尚未完全處理的資料。請參閱 [分析使用指南中的目前資料](../analyze/reports-analytics/current-data.md) 。
* **自訂連結：** 包含非頁面檢視資料的點擊類型。請參閱實施使用者指南中的 [s. tl()函數](../implement/js-implementation/function-tl.md) 。另請參閱「點擊」。
* **客戶屬性：** 允許上傳屬性資料的Experience Cloud功能。請參閱 [核心服務使用指南中的客戶屬性](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) 。
* **客戶支援代理人：** 獲得直接與Adobe客戶服務互動的指定使用者。請參閱 [Experience Cloud知識庫](https://helpx.adobe.com/experience-cloud/supported-users.html) 中的客戶支援委派。
* **資料收集伺服器：** 接收和處理資料的Adobe擁有的伺服器。影像要求會傳送至Adobe的資料收集伺服器，以便用於報告中。
* **資料連接器：** 完整的開發解決方案，可讓第三方自動化將資料上傳至Adobe Analytics。該第三方的客戶可以使用資料連接器在Adobe Analytics中豐富資料。大部分資料連接器使用類似於Data Sources中使用的工作流程。請參閱「匯入」使用指南中的「資料連接器」。
* **資料饋送：** 原始資料匯出，將每一次點擊列為一列和變數，作為個別欄。最常用來將Adobe Analytics資料匯出至第三方資料庫。請參閱 [「匯出」使用指南中的資料饋送](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) 。
* **資料來源：** 允許使用者將資料從檔案上傳至Adobe Analytics。檔案通常取自FTP網站。請參閱 [「匯入」使用指南中的「資料來源](../import/c-data-sources/datasrc-home.md) 」。
* **資料倉庫：** Adobe Analytics中允許您請求較大報表的功能。請參閱 [匯出使用指南中的資料倉庫](../export/data-warehouse/data-warehouse.md) 。
* **維度：** 包含變數值(如文字)的元件類型。範例包括頁面名稱、追蹤代碼或反向連結網域。量度通常是其對應項。
* **動態標籤管理：** Adobe之前的標籤管理解決方案。請參閱 [實施使用者指南中的DTM實作概述](../implement/c-implement-with-dtm/dtm-implementation-overview.md) 。Adobe建議您改用Adobe Experience Platform Launch。
* **事件序列化：** 實施措施以防止重復事件集合的程序。請參閱 [實施使用者指南中的事件序列化](../implement/js-implementation/event-serialization.md) 。
* **eVar：** 請參閱轉換變數。
* **事件：** 請參閱成功事件。
* **ExcelClient：** 不再用作詞語。報告建立工具的前身名稱。
* **有效期：** 在轉換變數的環境中，值持續存在於後端的時間長度。此持續性允許事件在事件點擊之前與變數值產生關聯。See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **流程：** 分析工作區中的視覺化類型，顯示使用者在您的網站上採取的路徑。請參閱 [分析使用指南中的流量視覺化](../analyze/analysis-workspace/visualizations/c-flow/flow.md) 。
* **Genesis：** 不再用作詞語。前一個資料連接器名稱。
* **全域報表套裝：** 指定給收集來自多個網站之點擊之報告套裝的非正式詞語。
* **H程式碼：** AppMeasurement的前身。在舊版Adobe Analytics中，程式碼版本是由「H版本」測量，例如H.27.5、H.26等。
* **點擊：** 傳送至Adobe資料收集伺服器的單一影像請求。頁面檢視和自訂連結都可稱為點擊。
* **影像要求：** 用來與Adobe資料收集伺服器通訊的透明1x像素影像。網站會要求此隱形影像包含包含資料的長查詢字串；Adobe會傳回不可見的影像，並剖析收到的查詢字串。
* **Insight：** 可以參考：
   * 前一個資料工作台名稱。
   * 自訂分析，自訂流量變數的歷史名稱。
* **KPI：** 縮寫效能指標的縮寫。協助企業瞭解其網站表現的量度。每個組織都有不同的KPI來衡量業務的不同層面。請參閱 [實施使用者指南中的建立解決方案設計文件](../implement/prepare/solution-design.md) 。
* **延遲：** 資料收集與報表可用時機之間的延遲。報告套裝中的典型延遲是30-90分鐘。請參閱 [TechNotes使用指南中的延遲。](../technotes/latency.md)
* **啓動：** Adobe目前實施解決方案Adobe Experience Platform Launch的簡稱。請參閱 [Adobe](https://docs.adobe.com/content/help/en/launch/using/overview.html) Experience Platform Launch使用指南中的「概述」。
* **清單prop：** 轉換一般流量變數以支援同一點擊中多個值的設定。如果已啓用設定，任何自訂流量變數都可以成為清單prop。請參閱 [實施使用者指南中的頁面變數](../implement/js-implementation/c-variables/page-variables.md) 。
* **清單變數：** 不同變數，不同於轉換變數。清單變數支援相同點擊中的多個值，而變數值則會在瀏覽中保留，類似於轉換變數。組織只能使用三個清單變數。請參閱 [實施使用者指南中的頁面變數](../implement/js-implementation/c-variables/page-variables.md) 。
* **登入公司：** 您的組織使用的報表套裝集合。有些組織有多家登入公司適用於其組織的不同部分。
* **行銷管道：** Adobe Analytics中根據訪客到達您網站的點擊分類的功能。用於分類點擊的邏輯可使用行銷渠道處理規則加以自訂。請參閱 [元件使用指南中的行銷管道](../components/c-marketing-channels/c-getting-started-mchannel.md) 快速入門。
* **度量：** 包含量化資料的元件類型。度量值通常包含數字，例如頁面檢視、瀏覽和收入。維度通常是其對應項目。
* **多套裝標記：** 將相同點擊傳送至多個報表套裝的做法。透過虛擬報表套裝的簡介，這種做法幾乎不再需要。大部分的多套裝標記努力都有助於因應全域報告套裝。
* **標準化：** 一種組織視覺化的方式，可將所有量度都納入相同比例，讓趨勢更易於比較。
* **發生次數：** 一種度量，可顯示維度值設定或持續存在的點擊數。請參閱 [元件使用指南中的發生次數](../components/c-variables/c-metrics/metrics-occurrences.md) 。
* **Omniture：** 不再用作詞語。Adobe在2009年被Adobe收購之前的組織。
* **路徑分析：** 請參閱流量。
* **頁面檢視：** 遞增頁面檢視的點擊類型。請參閱 [元件使用指南中的頁面檢視](../components/c-variables/c-metrics/metrics-page-view.md) 。另請參閱「點擊」。
* **永續性：** 轉換變數的抽象概念，可讓您在個別點擊上的變數值和事件之間進行連結。另請參閱「過期」。
* **主要伺服器呼叫：** 影像要求或點擊的替代名稱，主要用於多套裝標記和帳單的內容。當相同點擊傳送至多個報表套裝時，第一個報表套裝是主要伺服器呼叫，而其餘的則是次要伺服器呼叫。此規則適用於所有點擊類型，包括頁面檢視和連結追蹤。另請參閱次要伺服器呼叫。
* **處理規則：** 可以參考：
   * 處理規則，可在管理控制台中使用特定規則變更資料收集。See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * 行銷渠道處理規則，一組規則來決定點擊所屬的行銷渠道。請參閱 [管理使用者指南中的行銷管道處理規則](../admin/admin/marketing-channels-admin.md) 。
* **Prop：** 請參閱流量變數。
* **排名報表：** 通常遵循度量維度的報表格式。此類型的報表可讓您查看排名最前的項目，例如網站上檢視最多的頁面。另請參閱「趨勢」報表。
* **即時：** 在收集設定的變數時，幾乎不會延遲。請參閱 [管理使用者指南中的即時報告](../admin/admin/realtime/realtime.md) 。
* **報表套裝：** 您傳送資料的覆蓋容器。Adobe Analytics中的所有報表都會參考報表套裝。
* **滾動日期範圍：** 隨時間流逝而變更的相對日期範圍。例如，顯示最近天的報告可視為滾動日期範圍。另請參閱靜態日期範圍。
* **RSID：** 報表套裝ID的縮寫。報表套裝有好記名稱和報表套裝ID。
* **s. t()：** 在AppMeasurement程式庫中傳送頁面檢視影像請求的函數名稱。有些AppMeasurement程式庫會 `s.track()` 改用。請參閱 [實施使用者指南中的s. t()](../implement/js-implementation/function-t.md) 。
* **s<span>.</span>tl()：** AppMeasurement程式庫中傳送連結追蹤影像要求的函數名稱。有些AppMeasurement程式庫會 `s.trackLink()` 改用。請參閱 [實施使用者指南中的s. tl()](../implement/js-implementation/function-tl.md) 。
* **s_ code. js：** 用於Adobe Analytics歷史版本的JavaScript檔案名稱。使用的JavaScript檔案目前名稱為AppMeasurement. js。
* **衛星：** 不再用作詞語。動態標籤管理的舊產品名稱。
* **次要伺服器呼叫：** 影像要求或點擊的替代名稱，主要用於多套裝標記和帳單的內容。當相同點擊傳送到多個報表套裝時，第一個列出的報表套裝會是次要伺服器呼叫。另請參閱主要伺服器呼叫。
* **區段：** 可讓您專注於資料的特定子集。請參閱 [元件使用指南中的分段](../components/c-segmentation/seg-overview.md) 。
* **區段容器：** 區段的一部分，可決定要引入多少資料。容器可根據頁面檢視、瀏覽或訪客而定。請參閱 [元件使用指南中的分段](../components/c-segmentation/seg-overview.md) 。
* **序列化：** 請參閱事件序列化。
* **伺服器呼叫：** 影像要求或點擊的替代名稱，主要用於帳單內容。
* **單次存取：** 一種瀏覽，維度只有單一唯一值。只要沒有多個唯一值，瀏覽就可以多次點擊。請參閱 [元件使用指南中的單次存取](../components/c-variables/c-metrics/metrics-single-access.md) 。另請參閱「彈回數」。
* **SiteCatalyst：** 不再用作詞語。Adobe Analytics的舊產品名稱。
* **子關聯：** 不再用作詞語；取代為維度劃分。在舊版Adobe Analytics中，子關聯授予了劃分轉換變數的能力。請參閱 [分析使用指南中的劃分維度](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) 。
* **成功事件：** 使用者採取的追蹤動作。您的組織會決定追蹤要追蹤的事件，以及您用來追蹤的成功事件變數。請參閱 [元件使用指南中的自訂事件](../components/c-variables/c-metrics/metrics-custom.md) 。
* **支援的使用者：** 請參閱客戶支援委派。
* **流量變數：** 基本上稱為prop。儲存單一點擊的自訂值。舊版Adobe Analytics為prop提供獨特的值，但平台的改進讓自訂流量變數大放異彩。在大多數情況下，Adobe建議使用自訂轉換變數(eVar)。請參閱 [元件使用指南中的自訂流量變數](../components/c-variables/dimensionslist/reports-custom-traffic.md) 。
* **趨勢報表：** 通常會顯示具有度量之多個日期範圍的報表格式。此類型的報表可讓您檢視度量隨時間的表現。另請參閱排名報表。
* **獨特訪客**：代表瀏覽您網站的獨特個人人數。單一獨特訪客可以有多次瀏覽。請參閱 [元件使用指南中的獨特訪客](../components/c-variables/c-metrics/metrics-unique-visitors.md) 。
* **虛擬報表套裝：** 參照一般報表套裝並允許調整資料的虛擬容器。資料不會傳送至虛擬報表套裝；而是會傳送資料至一般報表套裝，而虛擬報表套裝則會建立在收集到的資料之外。請參閱 [元件使用指南中的虛擬報表套裝](../components/vrs/vrs-about.md) 。
* **請造訪：** 代表網站上發生的獨特作業數。請參閱 [元件使用指南中的瀏覽。](../components/c-variables/c-metrics/metrics-visit.md)
* **VISTA規則：** 由Adobe根據客戶要求複製、剖析或篩選資料伺服器端所建立的自訂邏輯。VISTA規則通常會產生額外的成本。另請參閱處理規則。
* **網頁信標：** 請參閱影像請求。

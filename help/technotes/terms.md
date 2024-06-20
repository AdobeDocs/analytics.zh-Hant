---
title: Adobe Analytics 中使用的詞彙
description: Adobe Analytics 辭彙表，定義常用詞彙。
exl-id: 07507ba1-a512-48d9-8022-6084de4ae262
feature: Implementation Basics
source-git-commit: f68cf0de5e7689d8245572b060a3d81c3bf85072
workflow-type: tm+mt
source-wordcount: '2528'
ht-degree: 98%

---

# Adobe Analytics 中使用的詞彙

使用此辭彙表來瞭解 Adobe Analytics 所使用各種詞彙的情境。

* **Activity Map：**&#x200B;一種瀏覽器外掛程式，可顯示網站上哪些區域的點按頻率最高。請參閱分析使用手冊中的 [Activity Map](/help/analyze/activity-map/activity-map.md)。
* **Admin Console：**&#x200B;可以指：
   * 舊版管理員工具，用於管理 Adobe Analytics 中的報告套裝設定。在舊版 Adobe Analytics 中，也需在此處管理使用者權限。請參閱管理員使用手冊中的[管理員工具](/help/admin/admin/c-admin-tools.md)。
   * Adobe Admin Console，可於此佈建產品存取權和管理使用者權限。請參閱管理員使用手冊中的 [Admin Console](/help/admin/admin-console/home.md)。
* **配置：**&#x200B;如果造訪期間轉換變數遇到多個值，變數的配置設定會決定要保留哪個值。請參閱管理員使用手冊中的[轉換變數](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。
* **Analysis Workspace：**&#x200B;用於建立強大、自訂的分析專案，並讓使用者都能自行獲得深入分析的瀏覽器解決方案。 提供優於 Reports and Analytics 的報告靈活性。
* **異常：**&#x200B;使用統計模式自動尋找資料中意外的趨勢時，可偵測出異常。此模式會分析量度並決定上下界限和值的預期範圍。請參閱分析使用手冊中的[異常偵測](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)。
* **AppMeasurement：**&#x200B;用來收集資料並傳送至 Adobe 的程式碼庫。請參閱實施作業使用手冊的[首頁](/help/implement/home.md)。
* **ASI 槽：**&#x200B;已不存在。在舊版 Adobe Analytics 中，ASI 槽提供暫時性報告套裝容器，可用於檢視分段資料。在目前版本的 Adobe Analytics 中，可立即將區段套用至任何報告。
* **劃分：**&#x200B;可讓您在另一個維度的內容中檢視維度。請參閱分析使用手冊中的[劃分維度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。
* **反彈：**&#x200B;包含單一點擊的造訪。請參閱元件使用手冊中的[反彈](/help/components/metrics/bounces.md)。另請見「單次存取」。
* **計算量度：**&#x200B;允許結合現有量度、統計函數和公式以便用於報告。請參閱元件使用手冊中的[計算量度](/help/components/c-calcmetrics/cm-overview.md)。
* **促銷活動：**&#x200B;可以指：
   * 促銷活動變數，會填入「追蹤代碼」維度。請參閱實施作業使用手冊中的[促銷活動](../implement/vars/page-vars/campaign.md)。
   * 「追蹤代碼」維度的預設分類；會自動為所有報告套裝建立。
   * Adobe Campaign，Adobe Experience Cloud 的一部分。請前往 [Adobe.com](https://www.adobe.com/tw/marketing/campaign.html) 取得更多資訊。
* **管道：**&#x200B;可以指：
   * 管道變數，會填入「網站區段」維度。請參閱實施作業使用手冊中的[頁面變數](/help/implement/vars/page-vars/page-variables.md)。
   * 行銷管道，此元件有助於瞭解使用者如何到達您的網站。請參閱元件使用手冊中的[行銷管道](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
* **分類：** Adobe Analytics 的一項功能，用於將維度項目分組。請參閱元件使用手冊中的[分類](/help/components/classifications/c-classifications.md)。
* **點按圖：**&#x200B;已停止使用。一種舊版瀏覽器外掛程式，可顯示網站上哪些區域的點按頻率最高。此工具已淘汰，改用Activity Map。
* **點按流資料摘要：**&#x200B;請見「資料摘要」。
* **同類群組：**&#x200B;指定的一段時間內具有共同特徵的一群人。請參閱分析使用手冊中的[同類群組分析是什麼？](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)。
* **收集伺服器：**&#x200B;請見「資料收集伺服器」。
* **元件：** Analysis Workspace 中的元件包含維度、量度、區段及時間範圍；您可將這些元件拖放至專案上。請參閱 Analyze 使用手冊中的「[元件概覽](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)」。
* **內容資料變數：**&#x200B;僅用於處理規則的暫時變數。如果處理規則未將內容資料變數值複製到轉換或流量變數中，便會永久遺失內容資料變數值。請參閱實施作業使用手冊中的[內容資料變數](../implement/vars/page-vars/contextdata.md)。
* **轉換變數：**&#x200B;也稱為 eVar。用於儲存自訂值及保留變數值，直到變數值過期為止。請參閱「元件」使用指南中的 [eVar](/help/components/dimensions/evar.md) 維度。
* **關聯：**&#x200B;不再作為詞彙使用；取代為維度劃分。在舊版 Adobe Analytics 中，關聯可用來劃分流量變數。請參閱分析使用手冊中的[劃分維度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。
* **自訂連結：**&#x200B;包含非頁面檢視資料的點擊類型。請參閱實施作業使用手冊中的 [s.tl() 函數](../implement/vars/functions/tl-method.md)。另請見「點擊」。
* **客戶屬性：**&#x200B;允許上傳屬性資料的 Experience Cloud 功能。請參閱核心服務使用手冊中的[客戶屬性](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html)。
* **客戶支援委派：**&#x200B;經授權可直接與 Adobe 客戶服務互動的指定使用者。請參閱 Experience Cloud 知識庫中的[客戶支援委派](https://helpx.adobe.com/tw/experience-cloud/supported-users.html)。
* **資料收集伺服器：** Adobe 所擁有的伺服器，用於接收及處理資料。影像請求會傳送至 Adobe 的資料收集伺服器，以用於報告。
* **資料聯結器：** 已淘汰的開發解決方案，可讓協力廠商將資料上傳至Adobe Analytics的作業自動化。 該協力廠商的客戶可使用資料連接器，讓其 Adobe Analytics 中的資料更為豐富。已取代為Adobe Exchange市集。
* **資料摘要：**&#x200B;原始資料匯出項目，會將每次點擊列為一列，並將變數列為個別欄。最常用於將 Adobe Analytics 資料匯出至協力廠商資料庫。請參閱匯出使用手冊中的[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)。
* **資料來源：**&#x200B;可讓使用者將資料從檔案上傳至 Adobe Analytics。通常會從 FTP 網站提取檔案。請參閱匯入使用手冊中的[資料來源](/help/import/data-sources/overview.md)。
* **Data Warehouse：** Adobe Analytics 的一項功能，可用來請求較大型的報告。請參閱匯出使用手冊中的 [Data Warehouse](/help/export/data-warehouse/data-warehouse.md)。
* **Data Workbench：**&#x200B;先前稱為 Insight。 專門設計來收集、處理、分析以及呈現多個管道的線上和離線客戶互動資料。
* **維度：**&#x200B;包含變數值 (如文字) 的元件類型。範例包括頁面名稱、追蹤代碼或反向連結網域。量度通常是其對應項目。
* **事件序列化：**&#x200B;防止收集重複事件的實施作業措施程序。請參閱實施作業使用手冊中的[事件序列化](../implement/vars/page-vars/events/event-serialization.md)。
* **eVar：**&#x200B;請見「轉換變數」。
* **事件**：請見「成功事件」。
* **ExcelClient：**&#x200B;不再作為詞彙使用。Report Builder 前身的名稱。
* **有效期限：**&#x200B;在轉換變數的內容中，值在後端持續存在的時間。此持續性可讓事件在事件點擊之前與變數值建立關聯。請參閱管理員使用手冊中的[轉換變數](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)。
* **流量：** Analysis Workspace 中的視覺效果類型，可顯示使用者在網站上行經的路徑。請參閱分析使用手冊中的[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)。
* **Genesis：**&#x200B;不再作為詞彙使用。資料連接器先前的名稱。
* **全域報告套裝：**&#x200B;為報告套裝指定的非正式詞彙，用於收集來自多個網站的點擊。
* **H 代碼：** AppMeasurement 的前身。在舊版 Adobe Analytics 中，程式碼版本是以「H 版本」(例如 H.27.5、H.26 等) 測量。
* **點擊：**&#x200B;傳送至 Adobe 資料收集伺服器的單一影像請求。頁面檢視和自訂連結都可稱為點擊。
* **影像請求：**&#x200B;透明的 1x1 像素影像，用於與 Adobe 資料收集伺服器通訊。網站透過包含資料的長查詢字串請求這個不可見的影像，接著 Adobe 會傳回不可見的影像，並剖析所收到的查詢字串。
* **Insight (分析)：**&#x200B;可以指：
   * Data Workbench 的前稱。
   * 自訂分析是自訂流量變數過去的名稱。
* **KPI：**&#x200B;關鍵績效指標的縮寫。可協助企業瞭解其網站成效的量度。每個組織都有不同的 KPI，可衡量其不同方面業務的成效。請參閱實施作業使用手冊中的[建立解決方案設計文件](/help/implement/prepare/solution-design.md)。
* **延遲：**&#x200B;收集到資料的時間和資料可在報告中使用的時間之間的延後情況。一般報告套裝的延遲為 30-90 分鐘。請參閱技術說明使用手冊中的[延遲](/help/technotes/latency.md)。
* **Launch：**&#x200B;不再當做詞彙使用。 Adobe Experience Platform 中的標記 (Adobe 目前的實作解決方案) 先前的簡稱。 請參閱 Adobe Experience Platform 使用手冊中的「[標記總覽](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)」。
* **清單 prop：**&#x200B;一種設定，可轉換一般流量變數以支援相同點擊中的多個值。如果已啟用此設定，任何自訂流量變數都可成為清單 prop。請參閱實施作業使用手冊中的 [prop](../implement/vars/page-vars/prop.md)。
* **清單變數：**&#x200B;與轉換變數區分開的不同變數。清單變數支援相同點擊中的多個值，而變數值會保留在造訪中，類似於轉換變數。一個組織只能使用三個清單變數。請參閱實施作業使用手冊中的[清單](/help/implement/vars/page-vars/list.md)。
* **登入公司**：貴組織所使用報告套裝的集合。某些組織擁有多個登入公司，適用於組織內的不同部門。
* **行銷管道：** Adobe Analytics 的一項功能，可依點擊到達您網站的方式分類點擊。可使用行銷管道處理規則來自訂用於分類點擊的邏輯。請參閱元件使用手冊中的[行銷管道快速入門](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。
* **量度：**&#x200B;包含量化資料的元件類型。度量值通常包含數字，例如頁面檢視次數、造訪次次數和營收。維度通常是其對應項目。
* **行動服務：**&#x200B;這是已淘汰的 Adobe 產品，可將整個 Adobe Experience Cloud 上行動應用程式的行動裝置行銷功能彙整在一起，好讓您了解並改進使用者與行動應用程式的互動。 
* **多套裝標記：**&#x200B;將相同點擊傳送至多個報告套裝的作法。隨著虛擬報告套裝的推出，此作法基本上已失去必要性。大部分的多套裝標記作業都有助於調整全域報告套裝。
* **正規化：**&#x200B;整理視覺化效果的方式，可納入所有量度並將其強制為等比例，以便更輕鬆進行趨勢比較。
* **發生次數：**&#x200B;一種量度類型，可顯示多少點擊已設定或存在某個維度項目。請參閱「元件」使用指南中的[發生次數](/help/components/metrics/occurrences.md)量度。
* **Omniture：**&#x200B;不再作為詞彙使用。2009 年 Adobe 收購 Adobe Analytics 之前擁有 Adobe Analytics 的組織。
* **路徑：**&#x200B;請見「流量」。
* **頁面檢視：**&#x200B;會增加頁面檢視次數的點擊類型。請參閱「元件」使用指南中的「[頁面檢視](/help/components/metrics/page-views.md)」量度。另請見「點擊」。
* **持續性：**&#x200B;轉換變數的抽象概念，可連結在不同點擊上發生的變數值和事件。另請見「有效期限」。
* **主要伺服器呼叫：**&#x200B;影像請求或點擊的替代名稱，主要用於多套裝標記和計費的情境下。將相同點擊傳送至多個報告套裝時，第一個報告套裝為主要伺服器呼叫，其餘則為次要伺服器呼叫。此規則適用於所有點擊類型，包括頁面檢視和連結追蹤。另請見「次要伺服器呼叫」。
* **處理規則：**&#x200B;可以指：
   * 處理規則，使用 Admin Console 中特定規則變更資料收集的一種方式。請參閱管理員使用手冊中的[處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)。
   * 行銷管道處理規則，判斷點擊所屬行銷管道的一組規則。請參閱管理員使用手冊中的[行銷管道處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)。
* **Prop：**&#x200B;請見「流量變數」。
* **排名報告：**&#x200B;一種報告格式，通常會依循含有量度的維度。此類型的報告可用於查看排名最前的項目，例如網站上檢視次數最多的頁面。另請見「趨勢報告」。
* **即時：**&#x200B;收集到所設定的變數時立即顯示，幾乎沒有或完全沒有延遲。請參閱管理員使用手冊中的[即時報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)。
* **Report Builder：** Microsoft Excel 增益集，可讓您從 Adobe Analytics 資料建立自訂請求。
* **報告套裝：**&#x200B;您所傳送資料的目的地總體容器。Adobe Analytics 中的所有報告都會參照報告套裝。
* **Reports &amp; Analytics：**&#x200B;先前稱為 SiteCatalyst。 用於報告和分析的瀏覽器解決方案。Analytics 套裝中的入門工具。此工具已[終止服務](https://experienceleague.adobe.com/docs/discontinued/using/reports-and-analytics.html)。
* **滾動式日期範圍：**&#x200B;隨時間推移而變更的相對日期範圍類型。例如，顯示過去 7 天的報告可視為滾動式日期範圍。另請見「靜態日期範圍」。
* **RSID：**&#x200B;報告套裝 ID 的縮寫。報告套裝同時具有好記的名稱和報告套裝 ID。
* **s.t()：**&#x200B;傳送頁面檢視影像請求的 AppMeasurement 資料庫中函數的名稱。有些 AppMeasurement 資料庫會改用 `s.track()`。請參閱實施作業使用手冊中的 [t](../implement/vars/functions/t-method.md)。
* **s<span>.</span>** tl()：傳送連結追蹤影像請求的 AppMeasurement 資料庫中函數的名稱。有些 AppMeasurement 資料庫會改用 `s.trackLink()`。請參閱實施作業使用手冊中的 [tl](../implement/vars/functions/tl-method.md)。
* **s_code.js：** Adobe Analytics 舊版本中使用的 JavaScript 檔案名稱。目前使用的 JavaScript 檔案名稱為 AppMeasurement.js。
* **Satellite：**&#x200B;不再作為詞彙使用。Dynamic Tag Management 的舊產品名稱。
* **次要伺服器呼叫：**&#x200B;影像請求或點擊的替代名稱，主要用於多套裝標記和計費的情境下。將相同點擊傳送至多個報告套裝時，所列出第一個報告套裝之後的所有報告套裝都是次要伺服器呼叫。另請見「主要伺服器呼叫」。
* **區段：**&#x200B;可讓您專注在特定資料子集上。請參閱元件使用手冊中的[分段](/help/components/segmentation/seg-overview.md)。
* **區段容器：**&#x200B;決定要傳入多少資料的區段部分。容器能以頁面檢視、造訪或訪客為依據。請參閱元件使用手冊中的[分段](/help/components/segmentation/seg-overview.md)。
* **序列化：**&#x200B;請見「事件序列化」。
* **伺服器呼叫：**&#x200B;影像請求或點擊的替代名稱，大多用於計費情境。
* **單次存取：**&#x200B;維度只有單一不重複值的造訪。只要沒有多個不重複值，該次造訪便可以有多個點擊。請參閱「元件」使用指南中的[單次存取](/help/components/metrics/single-access.md)量度。另請見「反彈」。
* **SiteCatalyst：**&#x200B;不再作為詞彙使用。Adobe Analytics 舊產品的名稱。
* **解決方案設計文件：**&#x200B;也稱為解決方案設計參考或 SDR。由組織維護的內部文件，概述如何使用自訂變數以及用來填入變數的邏輯。請參閱實施作業使用手冊中的[建立解決方案設計文件](/help/implement/prepare/solution-design.md)。
* **子關聯：**&#x200B;不再作為詞彙使用；取代為維度劃分。在舊版 Adobe Analytics 中，子關聯可用來劃分轉換變數。請參閱分析使用手冊中的[劃分維度](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)。
* **成功事件：**&#x200B;使用者採取的追蹤動作。貴組織需決定要追蹤哪些事件，以及使用哪些成功事件變數來追蹤這些事件。請參閱元件使用手冊中的[自訂事件](/help/components/metrics/custom-events.md)。
* **支援的使用者：**&#x200B;請見「客戶支援委派」。
* **流量變數：**&#x200B;也稱為 Prop。儲存單一點擊的自訂值。舊版 Adobe Analytics 為 prop 提供不重複值，但平台經過改良後，使得自訂流量變數大幅失去必要性。Adobe 建議在大多數情況下使用自訂轉換變數 (eVar)。請參閱「元件」使用指南中的 [Prop](/help/components/dimensions/prop.md) 維度。
* **趨勢報告：**&#x200B;一種報告格式，通常會以量度顯示多個日期範圍。這類型的報告可用來查看量度隨時間的表現。另請見「排名報告」。
* **不重複訪客**：代表造訪過您網站的不重複個人人數量。一個不重複訪客可以有多次造訪。請參閱「元件」使用指南中的[不重複訪客](/help/components/metrics/unique-visitors.md)量度。
* **虛擬報告套裝：**&#x200B;一種虛擬資料容器，會參照一般的報告套裝且允許調整資料。資料不會傳送至虛擬報告套裝，而是會傳送至一般報告套裝，而虛擬報告套裝是以收集到的資料為基礎所建立。請參閱元件使用手冊中的[虛擬報告套裝](/help/components/vrs/vrs-about.md)。
* **造訪：**&#x200B;代表網站上發生的不重複工作階段數。請參閱「元件」使用指南中的「[造訪](/help/components/metrics/visits.md)」量度。
* **VISTA 規則：** Adobe 在客戶請求複製、剖析或篩選資料伺服器端時建立的自訂邏輯。VISTA 規則通常會產生額外費用。另請見「處理規則」。
* **Web 信標：**&#x200B;請見「影像請求」。

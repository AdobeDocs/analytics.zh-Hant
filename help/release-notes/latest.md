---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: dabcb339238813b1da605a62f9a70599fbcef1bf
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 44%

---

# Adobe Analytics 目前的發行說明 (2026 年 2 月)

**上次更新日期**：2026年2月11日

這些發行說明涵蓋2026年2月發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新數次。 請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能和說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ---- |
| **已改善的資料摘要** <p>資料摘要現已提供下列改良功能：</p><ul><li>改善使用者體驗。</li><li>建立及管理欄範本的新體驗。</li><li>您現在可以選擇何時建立欄範本，以供日後資料摘要重複使用。 您也可以刪除、編輯和複製範本。<br/>以前，建立的每個資料摘要都會產生新的欄範本，導致大量未使用的欄範本無法刪除或管理。</li><li>依標籤新增及篩選。</li><li>檢視資料摘要作業的歷史記錄。 （要求期間開始時、開始時、完成時等）。</li><li>重新傳送或重新處理資料摘要。 （從「工作歷史記錄」頁面）</li><li>允許延遲送達點選。 您現在可以在設定的報告頻率內，包含資料摘要工作完成資料處理後所收到的資料。</li><li>為資料摘要選擇結束日期時，您選擇的結束日期會納入為資料摘要的最後一天。<br/>之前，結束日期已從資料摘要中排除。</li><li>現在可以提供15分鐘的匯出頻率，但預設無法使用。 若要讓此選項在您的環境中可用，您必須先聯絡Adobe客戶服務，要求將您的報表套裝設定為支援15分鐘匯出。</li></ul><p>**注意：**&#x200B;透過這些改善功能，Adobe Analytics中資料摘要頁面的URL也會更新。 請在2026年4月30日前更新任何現有書籤，以指向新的資料摘要頁面。</p><p>如需詳細資訊，請參閱[建立資料摘要](/help/export/analytics-data-feed/create-feed.md)和[管理資料摘要](/help/export/analytics-data-feed/df-manage-feeds.md)。</p> | 2026年1月20日 | 2026年2月24日<p>（原計畫於2026年2月10日發行）</p> |
| **依多個欄排序表格** <p>您現在可以在 Analysis Workspace 中依多個欄來排序自由格式表格的資料，無論其為維度或量度皆可。</p><p>當您排序多個欄的資料時，資料會根據您指派給每個欄的優先順序進行排序。優先順序編號會顯示在排序圖示旁邊。</p><p>如需詳細資訊，請參閱[篩選和排序自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **更新至近似計數相異函式**<p>Approximate Count Distinct函式中使用的HLL機率演演算法即將更新。 使用此函式的數字之結果輸出可能會和歷史數字稍有不同，如下所示：</p><ul><li>計算極少量不重複值時，結果將改善為使用精確計數，而不是使用預估值。</li><li>計算任何較大的數字時，計數估計將保持本次更新之前的準確性（估計準確性在準確數字的5%以內，即時間的95%）。</li></ul><p>如需Approximate Count Distinct函式的詳細資訊，請參閱[進階函式](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct)中的[Approximate Count Distinct](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> |  | 2026 年 3 月 |
| **串流媒體服務：支援排程資料** <p>您現在可以上傳過往串流媒體直播內容的排程資料，以便更輕鬆且更準確地追蹤觀看人數。</p><p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |
| **全新Adobe Analytics 2.0報表套裝API指南** <p>建立、擷取、更新及刪除報表套裝API。 如需詳細資訊，請參閱[Adobe Analytics 2.0報表套裝API參考指南](https://developer.adobe.com/analytics-apis/docs/2.0/apis/report-suites/)和[Adobe Analytics 2.0報表套裝API端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/report-suites/)。</p> | | 現已提供 |
| **全新Adobe Analytics 2.0 API異常偵測報告指南** <p>建立自動化API異常偵測報表。 如需詳細資訊，請參閱[異常偵測API報告端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/anomaly/)。</p> | | 現已提供 |
| **新Adobe Analytics 2.0 API基本日期趨勢報告指南** <p>建立自動化API基本日期趨勢KPI報告如需詳細資訊，請參閱[異常偵測API報告端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi/)。</p> | | 現已提供 |

## Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-424997、AN-424194、AN-425515、AN-423174、AN-425207、AN-428834、AN-306540、AN-426014、AN-427801
**分類**： AN-422723、AN-424467、AN-423724、AN-424003、AN-425217、AN-396062、AN-422744、AN-425456、AN-425271、AN-425655、AN-424894、AN-429236
**資料摘要和Data Warehouse**：AN-427082、AN-405154、AN-406512、AN-423594、AN-425283、AN-425208、AN-422510、AN-421189、AN-428986、AN-426724、AN-401525、AN-426884、AN-425146
**移轉**： AN-421192、AN-423443
**隱私權**：
**Report Builder**： AN-391415、AN-425125
**報告**： AN-422123、AN-425817、AN-421097、AN-422249、AN-403446、AN-424727、AN-426791、AN-427985
**排程報告**： AN-425484、AN-425137
**分段**： AN-428905、AN-428232
**Other**： AN-425054、AN-420190、AN-422248


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **直播串流處理改善** | 2026年1月14日 | Adobe計畫改善和變更LiveStream裝載的格式。 這些更新讓LiveStream和其他Adobe Analytics功能(例如Analysis Workspace)之間的對等性更佳。 預覽端點可供您測試計畫的變更。 如需變更的完整清單和預覽端點詳細資訊，請參閱[LiveStream發行說明](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)。 Adobe計畫在2026年4月13日將硬式轉換至更新的裝載格式。 |
| **移除TLS 1.2加密套件** | 2026年2月11日 | 管理員須知： Adobe預計於2026年5月27日從Adobe資料收集伺服器上移除下列TLS 1.2加密套裝的支援。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>大部分實施不需要客戶採取任何動作。 這項變更主要影響從使用過時TLS程式庫的舊版原生應用程式傳送的Analytics資料，以及在過時瀏覽器或作業系統上的少數網頁訪客。 移除對這些加密套裝的支援，可增強安全性，並使Adobe符合現代化的加密標準。 目前，不到0.1%的資料收集流量依賴這些加密套件。</p> |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。許多組織在為使用者提供增益集之前，須先完成內部核准流程。請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/?lang=zh-Hant)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [串流媒體服務發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

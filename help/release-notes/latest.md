---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7a245e2c24e8763c93150aa5b9f3ac2d197f6f1f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 54%

---

# Adobe Analytics 目前的發行說明 (2026 年 4 月)

**上次更新日期**：2026年4月9日

這些發行說明涵蓋2026年4月發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新數次。 請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能和說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ---- |
| **適用於Adobe Analytics的MCP伺服器** <br/>您現在可以使用MCP （模型內容通訊協定）將Adobe Analytics連結到您現有的代理式工作流程。 您可以使用自然語言來請求報表和深入分析。<p>(文件連結待補充。)</p> | | 2026年4月底 |
| **串流媒體服務：支援排程資料** <br/>您現在可以上傳過去直播串流媒體內容的排程資料，以更輕鬆準確地追蹤觀看率。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |
| **其他API日期範圍格式**<br/>&#x200B;現在支援兩種新格式，以便在Analytics 2.0 API報表請求中指定日期範圍。 這包括日期公式和混合格式。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | 2026 年 3 月 |
| **API報表要求中的選用維度**<br/>&#x200B;報表API要求中不需要維度物件。 如果未指定維度，回應會顯示總計報表的資料。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | 2026 年 3 月 |
| **日期趨勢進階API報告**<br/>&#x200B;全新Adobe Analytics 2.0 API日期趨勢進階報告指南。 使用日期範圍比較和區段建立進階日期趨勢API報表。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | 2026 年 3 月 |

## Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-442813、AN-442410、AN-441943、AN-441717、AN-434855、AN-431409、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**分類**：AN-443453、AN-443275、AN-443148、AN-442906、AN-442232、AN-442207、AN-442148、AN-442133、AN-441937、AN-441901、AN-441807、AN-441671、AN-441333、AN-441302、AN-441149、AN-441132、AN-441085、AN-441048、AN-440846、AN-440727、AN-440716、AN-440511、AN-440496 432100
**資料摘要和Data Warehouse**： AN-442211、AN-441719、AN-441183、AN-441011、AN-440625、AN-438953
**移轉**： AN-442467、AN-440380、AN-440357
**匯出**：
**Report Builder**： AN-441136、AN-438147、AN-425150
**報告**： AN-441506、AN-440919、AN-440545、AN-440300
**報表套裝**： AN-439429、AN-439423、AN-430988
**排程報告**：
**分段**：
**Other**： AN-423359、AN-406242、AN-397985


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **直播串流處理改善** | 2026年1月14日 | Adobe計畫改善和變更LiveStream裝載的格式。 這些更新讓LiveStream和其他Adobe Analytics功能（例如Analysis Workspace）之間的對等性更佳。 預覽端點可供您測試計畫的變更。 如需變更的完整清單和預覽端點詳細資訊，請參閱[LiveStream發行說明](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)。 Adobe計畫在2026年4月13日將硬式轉換至更新的裝載格式。 |
| **移除TLS 1.2加密套件** | 2026年2月11日 | 管理員須知： Adobe預計於2026年5月27日從Adobe資料收集伺服器上移除下列TLS 1.2加密套裝的支援。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>大部分實施不需要客戶採取任何動作。 這項變更主要影響從使用過時TLS程式庫的舊版原生應用程式傳送的Analytics資料，以及在過時瀏覽器或作業系統上的少數網頁訪客。 移除對這些加密套裝的支援，可增強安全性，並使Adobe符合現代化的加密標準。 目前，不到0.1%的資料收集流量依賴這些加密套件。</p> |
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

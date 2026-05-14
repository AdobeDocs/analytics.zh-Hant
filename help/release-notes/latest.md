---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 0cc9ef6fda26aca07c7cae5496b2ba53fcbbb316
workflow-type: tm+mt
source-wordcount: 1365
ht-degree: 61%

---

# 最新Adobe Analytics發行說明（2026年5月）

**上次更新日期**：2026年5月13日

這些發行說明涵蓋2026年5月發行期間。 Adobe Analytics 版本發行採用[持續傳遞模式](releases.md)，透過擴充性更高的分階段方式進行功能部署。 因此，這些發行說明每月會更新多次。 請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ---- |
| **適用於Adobe Analytics的MCP伺服器** <br/>Analytics MCP （模型內容通訊協定）伺服器可讓您將支援的MCP使用者端連線至Adobe Analytics。 在連線之後，您的MCP使用者端可以叫用產品特定工具來擷取資料、執行查詢，或執行支援的作業作為LLM或代理工作流程的一部分。 如需詳細資訊，請參閱[Analytics MCP伺服器](https://developer.adobe.com/analytics-mcp/docs/)。<p>如果您在Beta版使用這些MCP伺服器，請注意，Beta版和生產端點之間有不同的URL。 請確定在5月31日之前建立的任何代理工作流程均已更新為使用生產端點。</p> | | 2026年5月5日 |
| **Adobe Analytics中的歷程畫布** <br/>歷程畫布是Analysis Workspace中的視覺效果，可讓您通過分析人們如何進行或離開歷程，深入瞭解已定義的使用者歷程。 它可讓您建立節點和箭頭的彈性圖形，代表歷程中所包含的事件、維度專案和區段的任意組合。 將節點拖曳至畫布或重新排列歷程的事件和條件時，資料會更新。<p>歷程畫布先前僅適用於Customer Journey Analytics。</p><p>若要進一步瞭解Adobe Analytics中的Journey Canvas，請參閱[Journey Canvas概觀](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)。 </p><p>若要瞭解如何在Adobe Analytics中建置歷程畫布視覺效果，請參閱[設定歷程畫布](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。</p> | 2026年5月18日 | 2026年6月5日 |
| **歸因模型API報告指南** <br/>新的Adobe Analytics 2.0 API歸因模型報告指南已推出。 指南涵蓋如何在Dimension API報表中包含歸因模型物件資料。<p>如需詳細資訊，請參閱[Dimension API歸因模型](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/attmodel)。</p> | | 2026年5月 |
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-446522、AN-445779、AN-445759、AN-444676、AN-442813、AN-441943、AN-441717、AN-441538、AN-441123、AN-440976、AN-440952、AN-440919、AN-440599、AN-439797、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215、AN-、AN-、AN-
**分類**： AN-447743、AN-447296、AN-447130、AN-446552、AN-446324、AN-446040、AN-445841、AN-445753、AN-444992、AN-444979、AN-444428、AN-444332、AN-443507、AN-442906、AN-442232、AN-442207、AN-442133、AN-442035、AN-441901、AN-441807、AN-441671、AN-441333、AN-441302 AN-441267、AN-441132、AN-441085、AN-441048、AN-440846、AN-440727、AN-440716 440496 440429 432100
**資料摘要和Data Warehouse**： AN-447344、AN-446654、AN-445126、AN-444492、AN-442802、AN-442211、AN-442048、AN-441719、AN-441534、AN-441300、AN-441183、AN-441011、AN-440625
**移轉**： AN-442467、AN-440380、AN-440357
**匯出**：
**Report Builder**： AN-448697、AN-447128、AN-441148、AN-441136、AN-438147、AN-425150
**報告**： AN-445123、AN-444869、AN-443453、AN-443275、AN-443148、AN-442464、AN-442148、AN-441811、AN-441506、AN-441149、AN-441119、AN-440545、AN-440511、AN-440300、AN-431409、AN-423359 406242
**報表套裝**：
**排程報告**：
**分段**：
**其他**： AN-449159、AN-444661、AN-439429、AN-439423、AN-430988、AN-397985


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **LiveStream 處理改善** | 2026 年 1 月 14 日 | Adobe 計劃要改善及變更 LiveStream 承載的格式設定。 這些更新讓 LiveStream 和其他 Adobe Analytics 功能 (例如 Analysis Workspace) 之間擁有更好的功能對等性。 提供預覽端點，方便您測試所計劃的變更。 如需變更的完整清單和預覽端點的詳細資訊，請參閱 [LiveStream 發行說明](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)。 Adobe 計劃於 2026 年 4 月 13 日強制切換成更新後的承載格式。 |
| **移除 TLS 1.2 加密套裝** | 2026 年 2 月 11 日 | 管理員須知：Adobe 計劃於 2026 年 5 月 27 日從 Adobe 資料彙集伺服器移除對下列 TLS 1.2 加密套裝的支援。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>大部分實施不需要客戶採取任何動作。 這項變更主要影響由使用過時 TLS 程式庫的舊版原生應用程式傳送的 Analytics 資料，以及少數使用過時瀏覽器或作業系統的網頁訪客。 移除對這些加密套裝的支援，能增強安全性，並使 Adobe 符合現代化的加密標準。 目前，僅有不到 0.1% 的資料彙集流量需依賴這些加密套裝。</p> |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。 所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。 Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。 全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。 為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。 全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。 許多組織在為使用者提供增益集之前，須先完成內部核准流程。 請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。 為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。 此日期之後，舊版登入認證和舊版 SSO 將不再運作。 所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。 如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/?lang=zh-Hant)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hant)
* [串流媒體服務發行說明](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/release-notes/release-notes)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

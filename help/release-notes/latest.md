---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 91a17aa9ae7a0a6c6b7a1fd8d5ffe5d7d2efb294
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 94%

---

# 最新 Adobe Analytics 發行說明 (2025 年 6 月版本)

**上次更新日期**：2025年7月7日

這些發行說明涵蓋的發行期間為 2025 年 6 月 18 日至 7 月 15 日。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **具有演演算法的Livestream TNT欄位** | 直播串流正在重新整理，以確保技術持續現代且穩定。 作為重新整理的一部分，如果您的TNT欄位中有演演算法，我們將開始將TNT欄位併入直播串流輸出。 但是，這僅包括先前支援的元素： `campaignId`、`recipeId`、`trafficType`、`actionId`和`actionName`。 直播串流的整體TNT結構描述保持不變。 |   | 7,2025 年 7 月 |
| **對新 Report Builder 中安全雲端目的地的支援** | Javascript Report Builder 增益集現在支援將報告匯出到下列雲端儲存目的地：<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>以前，只有 FTP 和電子郵件目的地可使用。由於安全性考量，FTP 已不再受支援。</p><p>如需詳細資訊，請參閱[透過匯出到雲端目的地來安排活頁簿](/help/analyze/report-builder/report-builder-export.md)。</p><p>除了這些變更之外，在 Adobe Analytics 中建立位置時，「搭配使用」欄位現在提供了將位置與 Report Builder 搭配使用的選項，如[設定雲端匯入和匯出位置](/help/components/locations/configure-import-locations.md)中所述。</p> |  | 2025 年 6 月 19 日 (原定 6 月 18 日) |
| **全新預覽體驗** | 您建立區段或設定資料檢視的設定時所使用的預覽面板，現在會使用水平長條圖視覺化，而不是環狀圖視覺化。 |  | 2025 年 6 月 18 日 |
| **已修改歸因模型對話框** | 您現在可以在歸因模型對話框中分別定義容器及時段。 |  | 2025 年 6 月 18 日 |
| **客戶屬性 UI 的導覽已更新** | 現在可以直接從 Adobe Experience Cloud 中的應用程式選擇器存取客戶屬性使用者介面。 |  | 待定 |
| **串流媒體：支援排程資料** | 您現在可以上傳過往串流媒體直播內容的排程資料，以便更輕鬆且更準確地追蹤觀看人數。以下是支援排程資料上傳的直播內容範例：<ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或節目區段的觀看人數資料。無論您以何種方式實施串流媒體收集，都可以使用這些功能。<p>過去在分析直播內容時，很難準確地將特定工作階段連結至特定節目，亦無法將特定工作階段連結至個別主題或節目區段。了解更多 |  | 2025 年 8 月 15 日 (原定 2025 年 6 月 25 日) |

## Adobe Analytics 中的修正

**A4T**：AN-379045
**廣告分析**：AN-377338
**提醒**：AN-377229
**Analysis Workspace**：AN-378891；AN-379589；AN-379604；AN-381270；AN-382264；AN-382414；
**API 1.4**：AN-380188
**API 2.0**：AN-373078；AN-379006；AN-381248
**分類**：AN-379209；AN-379315；AN-379567；AN-379573；AN-379749；AN-379764；AN-379818；AN-380433；AN-381670；AN-381751；AN-381994；AN-382055；AN-382682；AN-383059；AN-383409
**貢獻度分析**：AN-369822
**資料摘要**：AN-365552；AN-367158；AN-378288；AN-379754；AN-380433；AN-380855；AN-380959；AN-381115；AN-381657；AN-381931
**Data Warehouse**：AN-379244
**平台**：AN-375847
**處理規則**：AN-375157
**Report Builder**：AN-371395；AN-372174；AN-373815；AN-383194
**伺服器呼叫**：AN-380930
**使用及存取記錄**：AN-372130；AN-382123
**虛擬報告套裝**：AN-382010


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/rb-overview)。Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。全新 Report Builder [功能幾乎與舊版相同](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)，並額外提供更多便利功能和 UI 增強設計。為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。許多組織在為使用者提供增益集之前，須先完成內部核准流程。請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 6 月 30 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證。從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[OAuth 新舊應用程式的實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |



## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d2f87c771ec2d5ab671cd8f022a2bd2e23a51ccb
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 45%

---

# 最新Adobe Analytics發行說明（2025年6月發行）

**上次更新日期**：2025年6月18日

這些發行說明涵蓋2025年6月18日至7月15日的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **支援新Report Builder中的安全目的地** | 新的匯出目的地已新增至Report Builder增益集。 支援下列雲端儲存空間目的地： <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> 基於安全性考量，不再支援FTP。 (文件連結待補充) |  | 2025年6月19日（原為6月18日） |
| **新的預覽體驗** | 預覽面板（用於預覽區段、計算量度等）現在使用橫條圖視覺效果，而非環形圖視覺效果。 |  | 2025 年 6 月 18 日 |
| **已修改的歸因模型對話方塊** | 您現在可以在歸因模型對話方塊中分別定義容器和時段。 |  | 18,2025 年 6 月 |
| **已更新客戶屬性UI的導覽** | 客戶屬性使用者介面現在可直接從Adobe Experience Cloud的應用程式選擇器存取。 |  | 待定 |
| **串流媒體：支援排程資料** | 您現在可以上傳過去直播串流媒體內容的排程資料，以更輕鬆準確地追蹤收視率。 以下是排程資料上傳支援的即時內容範例：<ul><li>FAST （免費廣告支援的電視）平台</li><li>本機串流</li><li>直播運動</li></ul>上傳排程資料可讓您追蹤在上傳檔案中指定的時間內，所執行的個別節目的收視率資料。 您甚至可以收集特定主題或計畫區段的收視率資料。 無論您如何實作串流媒體收集，都可以使用這些功能。<p>先前，在分析即時內容時，很難準確地將特定工作階段連結到特定計畫，也無法將特定工作階段連結到個別主題或計畫區段。 了解更多 |  | 2025 年 6 月 25 日 |

## Adobe Analytics 中的修正

**A4T**： AN-379045
**Advertising Analytics**： AN-377338
**警報**： AN-377229
**Analysis Workspace**： AN-378891；AN-379589；AN-379604；AN-381270；AN-382264；AN-382414；
**API 1.4**： AN-380188
**API 2.0**： AN-373078； AN-379006； AN-381248
**分類**： AN-379209、AN-379315、AN-379567、AN-379573、AN-379749、AN-379764、AN-379818、AN-380433、AN-381670、AN-381751、AN-381994、AN-382055、AN-382682、AN-383059、AN-383409
**貢獻分析**： AN-369822
**資料摘要**： AN-365552、AN-367158、AN-378288、AN-379754、AN-380433、AN-380855、AN-380959、AN-381115、AN-381657、AN-381931
**Data Warehouse**： AN-379244
**平台**： AN-375847
**處理規則**： AN-375157
**Report Builder**： AN-371395； AN-372174； AN-373815； AN-383194
**伺服器呼叫**： AN-380930
**使用與存取記錄檔**： AN-372130； AN-382123
**虛擬報告套裝**： AN-382010


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版Report Builder增益集將於2026年6月淘汰。 所有使用者應該開始將其舊版活頁簿升級至[新Report Builder](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/rb-overview)。 新的Report Builder可供Adobe Analytics和Customer Journey Analytics客戶使用。 它具有[接近功能同位性](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)以及許多便利的新功能和UI增強功能。 為了加快升級程式，新的Report Builder包含簡易的活頁簿轉換功能。 新的Report Builder只能透過Microsoft Store以增益集形式使用。 許多組織都需要內部核准流程，才可以讓使用者使用增益集。 請為此程式留出時間，並立即開始與您的組織合作，以確保在EOL日期之前有足夠的時間升級您的活頁簿。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 6 月 30 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證。從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[OAuth 新舊應用程式的實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API （版本1.4）** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |



## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

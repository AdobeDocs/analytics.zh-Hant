---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ace906a4b5acf1ab667529af33dd5be1618863f2
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 100%

---

# 最新 Adobe Analytics 版本發行說明 (2025 年 2 月發行)

**上次更新日期**：2025 年 2 月 21 日

這些發行說明涵蓋 2025 年 2 月 11 日至 2025 年 3 月中的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **交易 ID 保留期** | 90 天的交易 ID 保留期已延長至 25 個月`transactionID` 變數可唯一識別交易，因此點擊可繫結至透過資料來源上傳的資料。在[此處](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/vars/page-vars/transactionid)和[此處](https://experienceleague.adobe.com/zh-hant/docs/analytics/import/data-sources/transactionid)了解更多資訊。 |  | 2025 年 2 月 20 日 |
| **資料摘要 API 參考文件** | 資料摘要 API 的[參考文件](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs)現已可供使用。 |  | 2025 年 1 月 30 日 |
| **直播 API：用戶端實施** | 使用直播用戶端實施以使用直播資料。[了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | 2025 年 2 月 18 日 |
| **分類 API 更新內容** | 您現在可以從伺服器移除個別的分類欄位或金鑰。這是使用 DELETE 方法刪除整個分類資料集的替代方法。[了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | 2025 年 2 月 18 日 |
| **Analytics 上下文資料欄位更新內容`a.locale`** | 預定的更新將改變透過 Experience Edge 收集資料時 Analytics 上下文資料欄位`a.locale`的設定方式。使用 Experience Edge 將資料傳送至 Adobe Analytics 時，Analytics 欄位將根據 XDM 欄位的對應填入。`c.a.locale` 的對應引用了非標準 XDM 欄位 `xdm.environment.language`。此欄位將會經過更新，以引用正確的欄位 `xdm.environment._dc.language`。<p>此對應將持續引用 `xdm.environment.language`，以提供向後相容性。為維持連貫性，若兩個欄位皆已經過設定，則將以 `xdm.environment.language` 優先。您可以從[此處](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/xdm-var-mapping)檢視 XDM 對應至標準 Analytics 欄位的完整清單。 | | 2025 年 3 月 5 日 |


## Adobe Analytics 中的修正

**Analysis Workspace**：AN-359974；AN-366212；AN-368460
**分類**：AN-367186；AN-367328；AN-368548
**元件遷移**： AN-364529；AN-366398；AN-367509；
**資料摘要**：AN-365685；AN-366745；AN-367256；AN-367349；AN-368363
**Data Warehouse**：AN-368178；AN-368331；
**行動應用程式**：AN-367137
**平台**：AN-351924；AN-365540；AN-365866；AN-366898；AN-367856；AN-367933
**Report Builder**：AN-366456；AN-366655;
**虛擬報表套裝**：AN-367411
**VISTA 規則**：AN-365331

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **非 Campaign 客戶將無法存取觸發程序** | 2023 年 10 月 16 日 | 2025 年 1 月 30 日，沒有 Adobe Campaign 授權的 Adobe Analytics 客戶已無法設定和使用[觸發程序](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/services/triggers)。客戶需要購買 Campaign，或計劃停止使用觸發程序，或研究提供觸發程序功能的其他 Adobe 工具。 |

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 6 月 30 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證。從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 版本 (版本 2.27.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hant)。


## 相關資源

* [2024 年舊版發行說明](/help/release-notes/2024.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

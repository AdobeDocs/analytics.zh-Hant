---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 924f5f670d2f29269a5ba6623079e839f1fe8122
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 56%

---

# 最新Adobe Analytics發行說明（2025年2月發行）

**上次更新日期**：2024 年 2 月 21 日

這些發行說明涵蓋2025年2月11日到3月中旬的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **交易 ID 保留期** | 90天的交易ID保留期已延長至25個月。 `transactionID` 變數可唯一識別交易，因此點擊可繫結至透過資料來源上傳的資料。在[這裡](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid)和[這裡](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid)瞭解更多資訊。 |  | 2025年2月20日 |
| **資料摘要API參考** | 資料摘要API的[參考](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs)現已可用。 |  | 2025 年 1 月 30 日 |
| **Livestream API — 使用者端實作** | 使用Livestream使用者端實作來使用Livestream資料。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | 2025年2月18日 |
| **分類API的更新** | 您現在可以從伺服器移除個別分類欄位或金鑰。 這是使用DELETE方法刪除整個分類資料集的替代方法。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | 2025年2月18日 |


## Adobe Analytics 中的修正

**Analysis Workspace**： AN-359974； AN-366212； AN-368460
**分類**： AN-367186； AN-367328； AN-368548
**元件移轉**： AN-364529； AN-366398； AN-367509；
**資料摘要**： AN-365685； AN-366745； AN-367256； AN-367349； AN-368363
**Data Warehouse**： AN-368178； AN-368331；
**行動應用程式**： AN-367137
**平台**： AN-351924； AN-365540； AN-365866； AN-366898； AN-367856； AN-367933
**Report Builder**： AN-366456； AN-366655；
**虛擬報告套裝**： AN-367411
**VISTA規則**： AN-365331

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **即將更新Analytics內容資料欄位`a.locale`** | 2025年2月21日 | 將在2025年3月5日更新透過Experience Edge收集資料時如何設定Analytics內容資料欄位`a.locale`。 使用Experience Edge將資料傳送至Adobe Analytics時，Analytics欄位會根據XDM欄位對應填入。 `c.a.locale`的對映參考非標準XDM欄位`xdm.environment.language`。 此欄位將更新為參考正確的欄位`xdm.environment._dc.language`。  對應將繼續參考`xdm.environment.language`以回溯相容性。 若為連續性，如果兩個欄位都設定，則`xdm.environment.language`將取得優先權。 您可以在[這裡](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping)檢視從XDM對應至標準Analytics欄位的完整清單。 |
| **非 Campaign 客戶將無法存取觸發程序** | 2023 年 10 月 16 日 | 在2025年1月30日，沒有Adobe Campaign授權的Adobe Analytics客戶無法存取設定和使用[觸發器](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/services/triggers)的功能。 客戶需要購買 Campaign，或計劃停止使用觸發程序，或研究提供觸發程序功能的其他 Adobe 工具。 |

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 6 月 30 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證。從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hant)。


## 相關資源

* [2024 年舊版發行說明](/help/release-notes/2024.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

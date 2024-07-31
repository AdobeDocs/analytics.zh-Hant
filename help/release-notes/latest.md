---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: ht
source-wordcount: '732'
ht-degree: 100%

---

# 最新 Adobe Analytics 發行說明 (2024 年 7 月)

**上次更新日期**：2024 年 7 月 17 日

這些發行說明涵蓋 2024 年 7 月 17 日至 2024 年 8 月的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **針對連結追蹤的 Web SDK 改善** | 最新版本的 Web SDK 在連結追蹤方面提供了一些顯著的改善，使 Activity Map 直接受益。這些新功能在 Web SDK JavaScript 程式庫和 Web SDK 標記擴充功能中均可使用。<ul><li>事件分組：當訪客點擊內部連結時，您可以選擇對下一頁上的事件資料進行分組，而不是觸發單獨的事件呼叫以進行連結追蹤。此改善減少了 Web SDK 所用違反合約限制的事件數量。</li><li>篩選器點擊屬性：取代 `OnBeforeLinkClickSend` 的新回呼。您可以使用此回呼來篩選或混淆連結相關資料，然後再將其傳送到 Adobe。</li></ul><p>如需詳細資訊，請參閱 Web SDK 使用手冊中的 [clickCollection](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/commands/configure/clickcollection)。</p> | 公開 Beta 版於 2024 年 7 月 10 日開始 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正了使用者無法登入 Analytics UI 的問題 (AN-352953)
* 修正了使用者無法登入 Analytics 行動應用程式的問題 (AN-352463)
* 修正了無法將專案下載為 PDF 的問題 (AN-352680)
* 修正了未匯入分類的問題 (AN-352178)

### Analytics 其他修正

AN-352905；AN-352902；AN-352693；AN-352659；AN-352619；
AN-352577；AN-352575；AN-352572；AN-352571；AN-352549；AN-352501；AN-352499；AN-352478；AN-352466；AN-352437；AN-352378；AN-352355；AN-352341；AN-352318；AN-352297；AN-352272；AN-352267；AN-352263；AN-352088；AN-352019；AN-352018；AN-351978；AN-351908；AN-351809；AN-351750；AN-351689；AN-351624；AN-351564；AN-351524；AN-351507；AN-351416；AN-351414；AN-351405；AN-351299；AN-351283；AN-351231；AN-350710；AN-349912；AN-349786；AN-348300；AN-348061；AN-347865；AN-347676；AN-347478；AN-343611；AN-343114；AN-334124

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **13 個月的儲存有效期`cust_visids`** | 2024 年 5 月 22 日 | 即將發行的 Analytics Hit 處理引擎 (**預計於 2024 年 7 月發行**) 將開始強制執行 13 個月的 `cust_visids` 儲存有效期。如果報告套裝已啟用「啟用訪客聯繫」，則此設定用於尋找 `cust_visid` 是否有點擊時無 `cust_visid` 的 `visid_high/visid_low value`。目前，`visid_high/visid_low` 的 `cust_visid` 對應不會過期。在此版本中，如果自點擊時 `visid_high/visid_low` 有 `cust_visid` 以來已過去 13 個月或更長時間，對應會過期。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止更新並將關閉，使用這些服務的目前整合建置將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2024 年舊版發行說明](/help/release-notes/2024.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [串流媒體收集附加元件發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新。

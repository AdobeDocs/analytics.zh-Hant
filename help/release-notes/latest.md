---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ff5067a1f7d500c11737ddae507b431b875a44d9
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 76%

---

# 最新 Adobe Analytics 發行說明 (2024 年 8 月)

**上次更新日期**：2024年8月14日

這些發行說明涵蓋2024年8月14日至2024年9月的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **針對連結追蹤的 Web SDK 改善** | 最新版本的 Web SDK 在連結追蹤方面提供了一些顯著的改善，使 Activity Map 直接受益。這些新功能在 Web SDK JavaScript 程式庫和 Web SDK 標記擴充功能中均可使用。<ul><li>事件分組：當訪客點擊內部連結時，您可以選擇對下一頁上的事件資料進行分組，而不是觸發單獨的事件呼叫以進行連結追蹤。此改善減少了 Web SDK 所用違反合約限制的事件數量。</li><li>篩選器點擊屬性：取代 `OnBeforeLinkClickSend` 的新回呼。您可以使用此回呼來篩選或混淆連結相關資料，然後再將其傳送到 Adobe。</li></ul><p>如需詳細資訊，請參閱 Web SDK 使用手冊中的 [clickCollection](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/commands/configure/clickcollection)。</p> | 公開 Beta 版於 2024 年 7 月 10 日開始 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正Workspace中顯示多個未知值的問題(AN-353632)
* 修正在Admin Console中新增新客戶或新Analytics產品設定檔後，通知電子郵件未傳送的問題(AN-350930)

### Analytics 其他修正

AN-354361、AN-354248、AN-354211、AN-354324、AN-351532、AN-349808、AN-347831、AN-353777、AN-354092、AN-354064、AN-354202、AN-354006、AN-354097、AN-352548、AN-353819、AN-353818、AN-353628、AN-353747、AN-353527、AN-353490、AN-352647、AN-352656、AN-351274、AN-352135、AN-351519、AN-344906 AN-353697； AN-354499； AN-354402； AN-354062； AN-353905； AN-353932； AN-354142； AN-354194； AN-354182； AN-353758； AN-353039； AN-353612； AN-350799； AN-354414； AN-354636； AN-354249； AN-353637； AN-350949； AN-349402； AN-355103； AN-354174； AN-353823； AN-354819； AN-354215； AN-354219； AN-354040； AN-354763 AN-354597； AN-354478； AN-354528； AN-354335

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

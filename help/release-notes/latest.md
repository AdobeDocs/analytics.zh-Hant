---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 0bd4075a15edeeccdd9db8a70a1e871f9fc5af20
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 99%

---

# 最新 Adobe Analytics 版本注意事項 (2025 年 4 月發布)

**上次更新日期**：2025 年 4 月 16 日

這些發行說明涵蓋 2025 年 3 月 26 日至 5 月的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics 庫存** | Analytics 庫存提供您的 Adobe Analytics 環境的全面概觀，包括專案和元件的數量、報告套裝、使用者等資訊。藉由將庫存流程自動化，您可以快速了解從 Adobe Analytics 切換至 Customer Journey Analytics 所需的工作量。這會讓轉變的過程更加容易且快速。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/analytics-inventory) |  | 2025 年 3 月 26 日 |
| **Data Warehouse 專用維度** | 根據客戶回饋，我們決定重新評估。我們不會發佈先前宣布的自動 Data Warehouse 專用維度功能。 | | 待定 |

## Adobe Analytics 中的修正

**A4T**：AN-370625； AN-371279； AN-371351
**管理工具**：AN-365072； AN-371303
**Analysis Workspace**：AN-363831； AN-369554
**分類**：AN-370519； AN-370727； AN-370827； AN-370941； AN-370995； AN-371377； AN-371597； AN-371868； AN-371869； AN-372510； AN-372650； AN-373164； AN-373300； AN-373308； AN-373592
**資料收集**：AN-371877
**資料摘要**：AN-368676； AN-370225； AN-370514； AN-370521； AN-370687； AN-370761； AN-370911； AN-371047； AN-371542； AN-371627； AN-371746； AN-372708； AN-373068； AN-373179
**Data Warehouse**：AN-366649； AN-369817； AN-370705； AN-371127； AN-371995； AN-372596； AN-372940
**行銷管道**：AN-372308
**行動應用程式**：AN-370287； AN-371335； AN-371374
**平台**：AN-369510； AN-370435； AN-372150
**Report Builder**：AN-369830； AN-371395； AN-372983

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 不適用 |  |  |

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 6 月 30 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證。從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[OAuth 新舊應用程式的實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

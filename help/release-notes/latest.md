---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a7a80fc9845382eaa5b15dc6c325015de0a0cd9e
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 99%

---

# 最新 Adobe Analytics 發行說明 (2025 年 3 月發布)

**上次更新日期**：2025 年 3 月 12 日

這些發行說明涵蓋 2025 年 3 月 5 日至 5 月的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics 上下文資料欄位`a.locale`** 更新內容 | 這個更新將改變透過 Experience Edge 收集資料時 Analytics 上下文資料欄位 `a.locale` 的設定方式。使用 Experience Edge 將資料傳送至 Adobe Analytics 時，Analytics 欄位將根據 XDM 欄位的對應填入。`c.a.locale` 的對應引用了非標準 XDM 欄位 `xdm.environment.language`。此欄位將會經過更新，以引用正確的欄位 `xdm.environment._dc.language`。<p>此對應將持續引用 `xdm.environment.language`，以提供向後相容性。為維持連貫性，若兩個欄位皆已經過設定，將以 `xdm.environment.language` 優先。您可以從[此處](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/xdm-var-mapping)檢視 XDM 對應至標準 Analytics 欄位的完整清單。 | | 2025 年 3 月 5 日 |
| **Customer Journey Analytics 升級指南** | 讓您產生從 Adobe Analytics 升級到 Customer Journey Analytics 的逐步指南。這份指南是根據您的組織量身打造，而且會考量您目前的 Adobe Analytics 環境、您對 Customer Journey Analytics 的預期用途，以及您的組織想要做出之任何節省時間的權衡。<p>若要開始產生自訂指南，請先登入 [!DNL Customer Journey Analytics]，然後在「**[!UICONTROL 工作區]**」標籤上選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。<p>[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 2025 年 3 月 11 日 |
| **Data Warehouse 專用維度** | 2025 年 5 月起，Adobe 將開始將展現出極高基數的維度 (自訂變量，例如 eVar 和 props) 設定為「僅限 Data Warehouse」。高基數變數有許多不同的值；範例包括時間戳記或 UUID。這些維度將無法再用於 Analysis Workspace 中的報告。<p>需要進行此變更的候選項是月初就超出低流量限制的維度。對於這些類型的維度，Analysis Workspace 中基於該維度的報告毫無用處，因為可報告的資料僅代表所收集之初始值的一小部分。<p>由於 Data Warehouse 不會實施低流量限制，您仍然可以根據這些類型的維度建立實用的報告或區段。 | | 2025 年 5 月 |


## Adobe Analytics 中的修正

**Activity Map**：AN-361038
**管理工具**：AN-362178；AN-369483
**Analytics API 1.4**：AN-369615
**Analysis Workspace**：AN-353491；AN-363403；AN-367230；AN-367313；AN-368582；AN-369821；AN-370227；
**分類**：AN-369848；AN-370196；AN-370226；AN-370437
**資料摘要**：AN-366162；AN-368906；AN-369066；AN-369087；AN-369225；AN-369798
**資料治理**：AN-365157
**資料來源**：AN-367550
**平台**：AN-363931
**Report Builder**：AN-367460；AN-368975

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 不適用 |  |  |

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2025 年 1 月 17 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 6 月 30 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證。從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱[適用於 JavaScript 的 AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](/docs/analytics-platform/using/releases/latest$2$3?lang=zh-hant)
* [串流媒體收集發行說明](/docs/media-analytics/using/additional-resources/release-notes$2$3?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

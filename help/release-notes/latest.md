---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2a766fc06cab81c2b1d4b8a4de2c88dae42bf907
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 96%

---

# 最新 Adobe Analytics 發行說明 (2024 年 10 月 23 日發行)

**上次更新日期**： 2024年12月9日

這些發行說明涵蓋 2024 年 10 月 16 日至 2024 年底的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **適用於 Adobe Analytics 的新 Report Builder** | 新的 Report Builder 應用程式為 Adobe Analytics 帶來重大更新，包含改進的效能、簡化的使用者介面、2.0 API 支援以及對 Mac、Windows 和網頁瀏覽器上的 Microsoft Excel 的支援。此應用程式可以與舊版應用程式一起使用，但不能在同一檔案上使用。提供升級功能以將舊版活頁簿升級到新應用程式。[了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/report-buider-overview) |  | 2024 年 10 月 16 日 |
| **JSON Export 用於將標記實施遷移到 Web SDK 標記** | 此 Analytics 標記擴充功能的更新與遷移到 Web SDK 有關。您可以使用此 Adobe Analytics 標記擴充功能的更新作為工作流程的一部分，透過 Web SDK 擴充功能重新建立擴充功能設定。在 Adobe Analytics 標記擴充功能中，您可以將 eVar、Prop 和事件設定視為 JSON 格式，這些可以匯出以進行編輯並包含在 Web SDK 擴充功能中。 |  | 2024 年 10 月 31 日 |
| **有關 Analysis Workspace 效能的請求因素的新資訊** | 在 Analysis Workspace 中分析效能時，現在可以使用新的「請求因素」部分。如需深入了解如何處理請求以及影響處理時間的各種因素，請參閱 [Analysis Workspace 效能最佳化](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance)中的「請求因素」部分。 |  | 2024 年 10 月 1 日 |
| **交易ID保留期間** | `transactionID` 變數可唯一識別交易，因此點擊能與透過 Data Sources 上傳的資料連結。ID的預設保留期90天將從2025年1月起延長至25個月。 |  | 2025年1月22日 |

## Adobe Analytics 中的修正

Analysis Workspace：AN-356287；AN-358435；AN-359456；AN-359826；AN-360215
管理工具：AN-342485；AN-347931；AN-348704；AN-357723；AN-358453；AN-358717；AN-359548；AN-360136
分類：AN-359025；AN-359283；AN-359368；AN-359710；AN-359752；AN-359759；AN-359799；AN-359887；AN-360543；AN-360566；AN-360612；AN-360741；AN-360942；AN-360952
跨裝置分析：AN-359210
客戶屬性：AN-357897
資料收集：AN-351131；AN-351309；AN-355678；AN-359856
資料摘要：AN-359699
資料修復 API：AN-360256
資料來源：AN-359290
Data Warehouse：AN-359820
超額警示：AN-358132

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **非 Campaign 客戶將無法存取觸發程序** | 2023 年 10 月 16 日 | 2025 年 1 月 30 日，沒有 Adobe Campaign 授權的 Adobe Analytics 客戶將無法設定和使用觸發程序。客戶需要購買 Campaign，或計劃停止使用觸發程序，或研究提供觸發程序功能的其他 Adobe 工具。 |
| **自動對應其他實施細節 XDM 欄位** | 2024 年 9 月 11 日 | 使用 Adobe Experience Platform Edge Network 將資料傳送至 Adobe Analytics 時，XDM 欄位 `xdm.implementationdetails.name` 和 `xdm.implementationdetails.environment` 現在總是對應到內容資料變數 `c.a.x.implementationdetails.name` 和 `c.a.x.implementationdetails.environment`。過去某些情境會防止填入這些值。請調整任何相關的處理規則以配合這些值的可用性。 |

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hant)。


## 相關資源

* [2024 年舊版發行說明](/help/release-notes/2024.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hant)
* [串流媒體收集附加元件發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新。

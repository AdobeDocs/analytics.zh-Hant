---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ebe6716a3dde89d7212385c25044fb533d7737c2
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 100%

---

# 最新 Adobe Analytics 發行說明 (2025 年 7 月版本)

**上次更新日期**：2025 年 7 月 16 日

這些發行說明涵蓋 2025 年 7 月 7 日至 2025 年 8 月 15 日的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **透過演算法使用 Livestream 輸出 TNT 欄位** | 為確保技術持續保持現代化和穩定性，Livestream 正在進行更新。在此更新中，如果您的 TNT 欄位中包含演算法，我們將開始把 TNT 欄位合併至 Livestream 輸出。但是，這僅包括先前支援的元素：`campaignId`、`recipeId`、`trafficType`、`actionId` 以及 `actionName`。Livestream 的整體 TNT 結構語言保持不變。 |   | 2025 年 7 月 7 日 |
| **客戶屬性 UI 的導覽已更新** | 現在可以直接從 Adobe Experience Cloud 中的應用程式選擇器存取客戶屬性使用者介面。 | 2025 年 7 月 1 日 | 待定 |

## Adobe Analytics 中的修正

**Activity Map**：AN-360987
**Analysis Workspace**：AN-378094、AN-380979、AN-382908、AN-387652；
**分類**：AN-382412、AN-383157、AN-384616、AN-384803、AN-385933、AN-387320、AN-387351、AN-387832、AN-387833、AN-387839、AN-387915；
**資料集合**：AN-387661
**資料摘要**：AN-375172、AN-384369、AN-387859、AN-387952、AN-388155；
**平台**：AN-382813、AN-386627、AN-386815
**隱私權**：AN-384390
**Report Builder**：AN-388035
**報告**：AN-380441
**排程報告**：AN-378280、AN-378331
**區段比較**：AN-368766


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/rb-overview)。Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。全新 Report Builder [功能幾乎與舊版相同](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)，並額外提供更多便利功能和 UI 增強設計。為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。許多組織在為使用者提供增益集之前，須先完成內部核准流程。請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

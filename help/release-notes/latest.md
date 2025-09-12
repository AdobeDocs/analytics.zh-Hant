---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e1ae808920490f7d7c0611e45606a3f82b61ccdb
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 79%

---

# 最新Adobe Analytics發行說明（2025年9月發行）

**上次更新日期**：2025年9月11日

這些發行說明涵蓋2025年9月至10月初的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **改善將專案和元件移轉至Customer Journey Analytics時的效能** | 將專案和元件從Adobe Analytics移轉至Customer Journey Analytics時，現在可使用下列改良功能：<ul><li>一次移轉多個專案。<p>您一次最多可以移轉20個專案。</p><p>過去，您一次只能移轉一個專案。</p></li><li>針對已對應至先前專案移轉的維度和量度，更新其對應專案。<p>現在，即使相同的維度和量度先前已對應至先前的移轉，您每次移轉專案時都可以更新這些對應。</p><p>之前，您選擇的所有對應對於所有未來的專案移轉都是永久性的。</p></li><li>改善擁有大量專案的組織的效能。</li></ul><p>如需詳細資訊，請參閱[將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](/help/admin/tools/component-migration/component-migration.md)。</p> | 2025年9月15日 | 2025年9月18日 |
| **使用新的反向連結類型維度項目分析 AI 流量** | 10 月份將推出新的反向連結類型維度項目，以協助分析來自 AI 工具的流量。 <p>這項新的反向連結類型維度項目稱為「對話式 AI 工具」，可將主要 AI 工具的反向連結網域組成群組，讓您可以查看整個群組的趨勢。此新類別的初始反向連結網域清單包括 (但不限於)：</p><ul><li>chatgpt.com</li><li>Claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>新的維度項目將在所有 Adobe Analytics 相關工具中可供使用，包括 Analysis Workspace、Report Builder、Data Warehouse、資料摘要等。</p><p>使用新的維度項目時，請考慮以下事項：</p><ul><li>未必始終可區分反向連結流量是來自搜尋引擎「AI 模式」所提供的結果，還是來自傳統搜尋結果的點進次數。</li><li>新的對話式 AI 工具維度項目聚焦於流量最高的主要提供者。新趨勢顯示擁有與主要 AI 工具提供者相似網域的仿冒網站數量正逐步攀升。這可能是由於個人或群組可以輕鬆建立自己的 AI 工具並將其架設在網路上。由於這是一個快速發展的領域，如果您發現某個熱門網站未包含在內，請聯絡 Adobe 支援團隊。</li><li>反向連結類型維度 (包括新的對話式 AI 工具維度項目) 僅適用於透過 Adobe Analytics 所處理的資料。 </li></ul><p>(文件連結待補充。)</p> |   | 2025 年 10 月 |
| **串流媒體服務：XDM 欄位已更新，可將串流媒體資料收集至 Adobe Experience Platform 內** | 將串流媒體資料收集至 Adobe Experience Platform 時，不應再使用串流媒體參數文件中「XDM 欄位路徑」標題下所顯示的 XDM 欄位路徑。相對地，在 2025 年 5 月 9 日前實施 Analytics 來源連接器，將串流媒體資料收集至 Platform 內的客戶，必須將其現有設定移轉至 mediaReporting 欄位路徑 (如串流媒體參數文件之「報告 XDM 欄位路徑」標題下的內容所示)。<p> 這些欄位路徑位於下列頁面，並標記為「已棄用」：[音訊和視訊參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/player-state-parameters)，以及[品質參數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/quality-parameters)。(在 2025 年 5 月 9 日之後實作 Analytics 來源連接器，且僅使用 mediaReporting XDM 路徑的客戶，則無需採取任何行動。) </p><p>已棄用的 XDM 欄位路徑上的資料攝取將持續至 2025 年 10 月底。之後會完全移除已棄用的欄位路徑，且在 Adobe Experience Platform Schema UI 中不再顯示，而且只會使用 mediaReporting 欄位路徑傳送資料。</p><p>如需更多資訊，請參閱[將 Analytics 來源連接器實施移轉至已更新的 XDM 串流媒體欄位](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>如需移轉支援，請聯絡您的 Adobe Consulting 服務或帳戶團隊。 </p> |  | 2025 年 10 月 |

## Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-386791、AN-380838、AN-389373、AN-390851、AN-391593、AN-391404、AN-393064、AN-379337
**分類**： AN-391364、AN-393014、AN-393882、AN-394346、AN-394333、AN-390201
**資料彙集**： AN-388127
**資料摘要和Data Warehouse**： AN-391243
**隱私權**：
**Report Builder**： AN-387741、AN-386777、AN-388720、AN-389343
**報告**： AN-392863、AN-371871、AN-393640、AN-391334
**排程報告**： AN-391150、AN-390474
**區段比較**：
**Other**： AN-387858、AN-393985、AN-393287


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。許多組織在為使用者提供增益集之前，須先完成內部核准流程。請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [串流媒體服務發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

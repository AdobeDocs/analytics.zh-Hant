---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 07d6b4e096d239d4940f438c5eca46f496a18131
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 42%

---

# 最新Adobe Analytics發行說明（2025年8月發行）

**上次更新日期**：2025年8月13日

這些發行說明涵蓋2025年8月13日至9月16日的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用新的反向連結型別維度專案分析AI流量** | 10月時，將提供新的反向連結型別維度專案，以協助分析來自AI工具的流量。 <p>這個稱為交談AI工具的新反向連結型別維度專案會將主要AI工具的反向連結網域分組在一起，讓您檢視整個群組的趨勢。 此新類別中的初始反向連結網域清單包含（但不限於）：</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>新的維度專案將可在所有Adobe Analytics相關工具中使用，包括Analysis Workspace、Report Builder、Data Warehouse、資料摘要等。</p><p>使用此新維度專案時，請考量下列事項：</p><ul><li>並非總是能夠區分來自搜尋引擎「AI模式」中提供的結果的反向連結流量，與來自點進次數和傳統搜尋結果的反向連結流量。</li><li>新的交談AI工具維度專案會專注於具有最多流量的主要提供者。 新趨勢顯示越來越多與主要AI工具提供者網域類似的模擬者網站。 這可能是因為個人或群組可以輕鬆地建立自己的AI工具並在網際網路上託管。 由於這是快速發展的空間，如果您發現受歡迎網站並未包含在內，請聯絡Adobe支援團隊。</li><li>反向連結型別維度（包括新的「對話式人工智慧工具」維度專案）僅適用於Adobe Analytics處理的資料。 </li></ul><p>(後續文件連結。)</p> |   | 2025 年 10 月 |
| **以 PDF 格式下載的專案會下載至您的工作站** | 將專案下載為PDF時，PDF會下載至您工作站的下載資料夾。 <p>之前，將專案下載為PDF會在新的瀏覽器標籤中啟動PDF，並具有唯一的URL。</p><p>如需詳細資訊，請參閱[下載專案和資料](/help/analyze/analysis-workspace/curate-share/download-send.md)</p> |  | 2025 年 8 月 25 日 |
| **刪除的專案無法透過URL立即使用，且會從排程傳遞中刪除** | 刪除的專案會立即從排程傳遞中刪除，且無法再透過其URL存取。<p>以往，專案會包含在已排程的傳送中，且在刪除後的60天內，都可使用其URL進行存取。</p><p>如需有關刪除專案的詳細資訊，請參閱[專案概述](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)。</p> | | 2025年8月底 |
| **串流媒體：更新將串流媒體資料收集到Adobe Experience Platform的XDM欄位** | 將串流媒體資料收集至 Adobe Experience Platform 時，不應再使用串流媒體參數文件中「XDM 欄位路徑」標題下顯示的 XDM 欄位路徑。反之，在2025年5月9日之前實作Analytics來源聯結器以收集串流媒體資料至Platform的客戶必須將其現有設定移轉至mediaReporting欄位路徑，如串流媒體引數檔案的「報告XDM欄位路徑」標題下所示。<p> 這些欄位路徑可在下列頁面上找到，並標示為「已棄用」： [音訊和視訊引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[廣告引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/ad-parameters)、[章節引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器狀態引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/player-state-parameters)以及[品質引數](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/implementation/variables/quality-parameters)。 （在2025年5月9日之後實施Analytics來源聯結器，而且已經只使用mediaReporting XDM路徑的客戶不需要採取任何動作。）</p><p>淘汰XDM欄位路徑上的資料內嵌將持續到2025年10月底。 之後，已棄用的欄位路徑將完全移除，不再顯示於Adobe Experience Platform結構描述UI中，而且只會使用mediaReporting欄位路徑傳送資料。</p><p>如需詳細資訊，請參閱[將Analytics Source Connector實作移轉至更新的XDM串流媒體欄位](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>如需移轉支援，請聯絡您的Adobe Consulting服務或帳戶團隊。 </p> |  | 2025 年 10 月 |

## Adobe Analytics 中的修正

**Activity Map**： AN-389205； AN-384186
**Analysis Workspace**： AN-390102、AN-389066、AN-388841、AN-388687、AN-388478、AN-387089、AN-387044、AN-384560、AN-379213、AN-351639
**分類**： AN-390442、AN-390385、AN-389953、AN-389703、AN-389321、AN-389116、AN-388833、AN-388717、AN-387987、AN-383329
**資料彙集**： AN-389320
**資料摘要和Data Warehouse**： AN-389702； AN-388136； AN-387779； AN-384369； AN-383075； AN-380307
**隱私權**：
**Report Builder**： AN-389336； AN-382775
**報告**： AN-390398
**排程報告**：
**區段比較**：
**Other**： AN-388180； AN-383164； AN-366532


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

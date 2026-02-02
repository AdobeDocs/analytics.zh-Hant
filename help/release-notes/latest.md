---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1ef9c5fc39174f9b0313fc8b738ed0da35273c18
workflow-type: tm+mt
source-wordcount: '1231'
ht-degree: 53%

---

# 最新 Adobe Analytics 版本注意事項 (2026 年 1 月)

**上次更新日期**：2026 年 1 月 14 日

這些發行說明涵蓋 2026 年 1 月的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **分類集規則產生器** | 分類集中現在提供[規則產生器](/help/components/classifications/sets/manage/rules.md)功能。 您可以在分類設定的內容中定義規則。 規則會套用（啟動時）到訂閱分類集的所有報表套裝和索引鍵維度組合。</p> |  | 2026年1月23日 |
| **已改善的資料摘要** | 資料摘要提供下列改良功能：<ul><li>改善使用者體驗。</li><li>建立及管理欄範本的新體驗。</li><li>您現在可以選擇何時建立欄範本，以供日後的資料摘要重複使用。 您也可以刪除、編輯和複製範本。<br/>以前，建立的每個資料摘要都會產生新的欄範本，導致大量未使用的欄範本無法刪除或管理。</li><li>依標籤新增及篩選。</li><li>檢視資料摘要作業的歷史記錄。 （要求期間開始時、開始時、完成時等）。</li><li>重新傳送或重新處理資料摘要。 （從「工作歷史記錄」頁面）</li><li>允許延遲送達點選。 您現在可以在設定的報告頻率內，包含資料摘要工作完成資料處理後所收到的資料。</li><li>為資料摘要選擇結束日期時，您選擇的結束日期會納入為資料摘要的最後一天。<br/>之前，結束日期已從資料摘要中排除。</li><li>現在可以提供15分鐘的匯出頻率，但預設無法使用。 若要讓此選項在您的環境中可用，您必須先聯絡Adobe客戶服務，要求將您的報表套裝設定為支援15分鐘匯出。</li></ul><p>**注意：**&#x200B;透過這些改善功能，Adobe Analytics中資料摘要頁面的URL也會更新。 請在2026年4月30日前更新任何現有書籤，以指向新的資料摘要頁面。</p>(文件連結待補充。)</p> | 2026年1月20日 | 2026年2月24日 <p>（原計畫於2026年2月10日發行）</p> |
| **依多個欄排序表格** | 您現在可以在 Analysis Workspace 中依多個欄來排序自由格式表格的資料，無論其為維度或量度皆可。<p>當您排序多個欄的資料時，資料會根據您指派給每個欄的優先順序進行排序。優先順序編號會顯示在排序圖示旁邊。</p><p>如需詳細資訊，請參閱[篩選和排序自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **串流媒體服務：支援排程資料** | 您現在可以上傳過往串流媒體直播內容的排程資料，以便更輕鬆且更準確地追蹤觀看人數。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>(原規劃於 2025 年 10 月 29 日發行)</p> |

## Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-423389、AN-422636、AN-422482、AN-422027、AN-421134、AN-420187、AN-406271、AN-406188、AN-405997、AN-405983、AN-405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713、AN-404502、AN-404353、AN-404352、AN-404048、AN-402523、AN-396149、AN-390990 an-390728、AN-390646、AN-383484、AN-376980 371729 347570
**分類**：AN-423985、AN-423092、AN-423067、AN-422913、AN-422908、AN-422793、AN-422785、AN-422745、AN-422705、AN-422422、AN-422126、AN-422098、AN-422077、AN-422058、AN-421999、AN-421698、AN-421351、AN-406583、AN-406295、AN-406123、AN-406052、AN-404743、AN-404372
**資料彙集**： AN-422488
**資料摘要和Data Warehouse**： AN-423186、AN-422789、AN-422239、AN-421552、AN-421393、AN-421339、AN-421231、AN-420149、AN-406345、AN-406217、AN-405073、AN-404822、AN-404774、AN-389691
**隱私權**：
**Report Builder**： AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**報告**：
**排程報告**： AN-423087、AN-422686
**區段比較**：
**Other**： AN-423401、AN-422819、AN-422775、AN-422626、AN-422238、AN-422160、AN-422071、AN-421687、AN-420045、AN-404891、AN-404608、AN-390912


## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **直播串流處理改善** | 2026年1月14日 | Adobe計畫改善和變更LiveStream裝載的格式。 這些更新讓LiveStream和其他Adobe Analytics功能(例如Analysis Workspace)之間的對等性更佳。 預覽端點可供您測試計畫的變更。 如需變更的完整清單和預覽端點詳細資訊，請參閱[LiveStream發行說明]。 Adobe計畫在2026年4月13日將硬式轉換至更新的裝載格式。 |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。許多組織在為使用者提供增益集之前，須先完成內部核准流程。請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **透過舊版網域或舊版 SSO 進行存取** | 2025 年 4 月 10 日 | Adobe 計畫更新使用者存取 Adobe Analytics 的方式，以增強安全性並簡化您的登入體驗。為此，透過舊版網域或舊版 SSO (包括 `my.omniture.com`) 進行存取的功能，將於 **2026 年 1 月 2 日**&#x200B;永久停止。此日期之後，舊版登入認證和舊版 SSO 將不再運作。所有使用者都必須使用其 Adobe Experience Cloud ID 透過 `experience.adobe.com` 登入。如果您需要有關 Experience Cloud ID 的協助，請聯絡您所在組織的 Adobe Analytics 管理員或 [Adobe 客戶服務](https://helpx.adobe.com/tw/contact.html)。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/?lang=zh-Hant)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


## 相關資源

* [2025 年舊版發行說明](/help/release-notes/2025.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [串流媒體服務發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1bb989f3a7e1367ddc1cc2d88bcde9aa680ff963
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 62%

---

# Adobe Analytics 目前的版本注意事項 (2023 年 2 月)

**上次更新日期**：2023 年 2 月 13 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新資料隱私權標籤的使用者介面** | 更新後的介面可簡化報表套裝元件建立、管理和編輯資料隱私權標籤的程式。 [了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | 不適用 | 2023 年 2 月 8 日 |
| **在 Mobile 計分卡中隱藏比較日期範圍** | 使用行動計分卡，您可以切換 **[!UICONTROL 包含比較日期]** 設定來檢視或隱藏比較日期。 | 不適用 | 2023 年 2 月 8 日 |
| **Workspace 中的行事曆更新** | <ul><li>錨點面板日期：您可以使日期範圍元件相對於面板行事曆。 [了解更多](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>行事曆樣式更新：整個 UI 的行事曆樣式已升級，展現更為一致易用的工作流程。</li><li>行事曆公式更新：如果您使用相對日期，所有行事曆公式將反映面板日期範圍的開始。 [了解更多](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | 不適用 | 2023 年 2 月 8 日 |
| **Adobe Analytics Source Connector 串流傳輸的行/列篩選** | Adobe Experience Platform 中的 Analytics Source Connector 現在允許篩選 Analytics 資料；這類資料是用來在[即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)中填入設定檔。列層級篩選有助減少與設定檔有關聯的事件數量。 欄層級篩選有助於減少事件本身的豐富性，進而讓您最佳化設定檔權益的使用。 這項篩選僅適用於傳送至即時客戶設定檔和[身份服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant)的資料。**篩選不會影響傳送到資料湖的資料；這類資料是供 Customer Journey Analytics** 等應用程式使用。 [了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant#filtering-for-profile) | 不適用 | 2023 年 2 月 22 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

-302282；AN-303127；AN-303541；AN-303550；AN-305282；AN-306504；AN-307351；AN-307496；AN-307530；AN-307947；AN-308497；AN-；AN-308610；AN-308777；AN-308994；AN-309143；AN-309404；AN-309414；AN-309445；AN-309575；AN-309630；AN-309658；AN-309690；AN-309742；AN-309861；AN-309967；AN-309973；AN-310059；AN-310132；AN-310168；AN-310238；AN-310241；AN-310301；AN-310318；AN-310324；AN-310335；AN-310338；AN-310460；AN-310500；AN-310684；AN-310690；AN-311010；AN-311022；AN-311043；AN-311125；AN-311250；AN-311370；AN-311458;

## 給 Adobe Analytics 管理員的重要通知

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **自動遷移到分類集體系結構** | 2023 年 2 月 8 日 | Adobe計畫在未來數月將所有組織中的所有分類移轉到最新的分類架構。 最後一個要遷移的客戶預計於2023年5月完成。 不需要客戶操作，也不需要停機時間。 此新架構有許多優點，包括：<ul><li>大幅縮短處理時間(72小時→ 24小時)</li><li>使用 [分類集](/help/components/classifications/sets/overview.md) UI</li><li>未來在Adobe Experience Platform中使用分類資料的選項，透過 [Adobe Analytics來源連接器（分類資料）](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>請注意下列可能影響組織工作流程的變更：<ul><li>使用瀏覽器或FTP匯入時，「[!UICONTROL 衝突時覆蓋]「一律啟用。</li><li>使用瀏覽器或FTP匯入時，不再支援在匯入後立即匯出的選項。</li><li>Analytics 2.0 API `GetDimensions` 端點現在會為分類傳回字串識別碼，而非數值識別碼。 數值識別碼仍可使用，但Adobe建議盡可能使用新的字串識別碼。 數值識別碼可透過 `?expansion=hidden` 查詢字串參數。</li></ul>如果您想要組織有更具體的移轉排程，或對此移轉有疑問/疑慮，請聯絡Adobe客戶服務。 [了解更多](/help/components/classifications/sets/overview.md) |
| **依據 Google 用戶端提示更新裝置查詢** | 2023 年 1 月 25 日 | **2023 年 2 月 16 日** 將開始在裝置查詢中使用用戶端提示。 <p> <p>自 2022 年 10 月起，即可使用 Web SDK 或 AppMeasurement JavaScript 庫收集用戶端提示。 但直到 2023 年 2 月，用戶端提示才會被納入裝置查詢中。 屆時，在為來自 Chromium 瀏覽器 (例如 Google Chrome 和 Microsoft Edge) 的點擊取得某些裝置資訊時，除了使用者代理程式之外，Adobe 將開始使用用戶端提示。 這是為了因應 Google 計劃逐漸減少從使用者代理字串呈現的資訊，以取代透過用戶端提示傳遞的資料。 <p> <p>作為此變更的一部分，Adobe 將使用 Device Atlas 進行所有和使用者代理程式相關的裝置查找。[了解更多](/help/technotes/client-hints.md) |

{style=&quot;table-layout:auto&quot;}

## 終止服務(EOL)通知

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **終止日文功能電話跟蹤服務** | 2023 年 2 月 13 日 | 僅適用於日本客戶：2023年5月底，日文功能電話追蹤服務(mod_ktrack)將停止提供。 很抱歉，我們要求您卸載或禁用Apache伺服器上安裝的模組。 見第27和28頁 [此文檔](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) 以供參考。 |
| **部分Reports &amp; Analytics和Report Builder排程功能終止** | 2023 年 2 月 9 日 | 下列排程功能已於2023年1月31日終止：<ul><li>每小時任務的「x次後結束」選項(Report Builder</li><li>可在Reports and Analytics中排程新報表和下載資料擷取</li></ul><p>**附註**:我們最初於2022年4月終止這些功能，但已復原變更。 我們還發送通知，說明這些功能正在暫時恢復，並將於2023年1月31日重新終止。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，發佈清單預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有發佈清單，來傳送或排程 Analysis Workspace 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

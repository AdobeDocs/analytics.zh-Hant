---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e7140b78b7b2c6c63cb93f1341581cc83af7b33b
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 70%

---

# Adobe Analytics 目前的版本注意事項 (2023 年 2 月)

**上次更新日期**：2023 年 2 月 2 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新資料隱私權標籤的使用者介面** | 更新後的介面可簡化報表套裝元件建立、管理和編輯資料隱私權標籤的程式。 [了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | 不適用 | 2023年2月8日 |
| **行動計分卡中的比較日期範圍** | 使用行動計分卡，您可以切換 **[!UICONTROL 包含比較日期]** 設定來檢視或隱藏比較日期。 | 不適用 | 2023年2月8日 |
| **工作區中的日曆更新** | <ul><li>錨點面板日期：您可以建立與面板日曆相對的日期範圍元件。 [了解更多](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>日曆樣式更新：UI中的日曆樣式已升級，以呈現更一致且易於使用的工作流程。</li><li>日曆公式更新：如果您使用相對日期，所有日曆公式都會反映面板日期範圍的開始。 [了解更多](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | 不適用 | 2023年2月8日 |
| **Adobe Analytics Source Connector串流的列/欄篩選** | Adobe Experience Platform中的Analytics來源連接器現在允許篩選用於填入設定檔的Analytics資料 [即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant). 列層級篩選有助於減少與設定檔相關聯的事件數。 欄層級篩選有助於減少事件本身的豐富性，進而讓您最佳化設定檔權益的使用。 此篩選僅適用於傳送至「即時客戶設定檔」的資料，以及 [Identity服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant). **篩選不會影響傳送至Data Lake以用於應用程式(例如Customer Journey Analytics)的資料**. [了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | 不適用 | 2023 年 2 月 22 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

-302282；AN-303127；AN-303541；AN-303550；AN-305282；AN-306504；AN-307351；AN-307496；AN-307530；AN-307947；AN-308497；AN-；AN-308610；AN-308777；AN-308994；AN-309143；AN-309404；AN-309414；AN-309445；AN-309575；AN-309630；AN-309658；AN-309690；AN-309742；AN-309861；AN-309967；AN-309973；AN-310059；AN-310132；AN-310168；AN-310238；AN-310241；AN-310301；AN-310318；AN-310324；AN-310335；AN-310338；AN-310460；AN-310500；AN-310684；AN-310690；AN-311010；AN-311022；AN-311043；AN-311125；AN-311250；AN-311370；AN-311458;

## 給 Adobe Analytics 管理員的重要通知

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **遵循 Google 用戶端提示更新裝置查詢** | 2023 年 1 月 25 日 | **2023 年 2 月 16 日** 將開始在裝置查詢中使用客戶端提示。 <p> <p>自 2022 年 10 月起，即可使用 Web SDK 或 AppMeasurement JavaScript 庫收集用戶端提示。 但直到 2023 年 2 月，用戶端提示才會被納入裝置查詢中。 屆時，在為來自 Chromium 瀏覽器 (例如 Google Chrome 和 Microsoft Edge) 的點擊取得某些裝置資訊時，除了使用者代理程式之外，Adobe 將開始使用用戶端提示。 這是為了因應 Google 計劃逐漸減少從使用者代理字串呈現的資訊，以取代透過用戶端提示傳遞的資料。 <p> <p>作為此變更的一部分，Adobe 將使用 Device Atlas 進行所有和使用者代理程式相關的裝置查找。[了解更多](/help/technotes/client-hints.md) |
| **暫停 Reports &amp; Analytics 中的排程報告** | 2023 年 1 月 6 日 | Adobe已於 **2023年1月31日**. 請注意，報告和資料擷取的到期窗口限制仍維持九個月；報告和資料擷取的傳送將在此期間結束時暫停，除非重新啟用排程。<p>在2023年1月31日之前，您必須將排程報表移轉至Adobe Analytics中可供您使用的其他機制之一。 如有其他問題或需要支援，請和 Adobe 客戶服務聯絡。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **暫停 Report Builder 中的排程工作** | 2023 年 1 月 6 日 | 開啟 **2023年1月31日**,Adobe會在Report Builder中對排程任務進行變更，作為效能和傳送最佳化工作的一部分。 這些變更包括移除讓已排程傳遞「在 x 次發生次數後結束」的功能。<p>您可繼續排程每小時的 Report Builder 工作，並使其在最多 99 次發生次數後結束。請注意，復原作業僅適用於每小時工作；所有其他傳遞間隔 (每日、每週、每月和每年) 仍無法使用「x 次發生次數後結束」功能。如有更多問題或需要支援，請聯絡 Adobe 客戶服務。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## 生命週期結束重要通知

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，發佈清單預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有發佈清單，來傳送或排程 Analysis Workspace 專案。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

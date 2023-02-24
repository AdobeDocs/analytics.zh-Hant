---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5eefd324cfb1d9985f21faf3809e889802c96e0c
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 90%

---

# Adobe Analytics 目前的版本注意事項 (2023 年 2 月)

**上次更新日期**：2023 年 2 月 23 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **更新了資料隱私權標籤的使用者介面** | 更新後的介面簡化了為報告套裝元件建立、管理和編輯資料隱私權標籤的過程。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=zh-Hant) | 不適用 | 2023 年 2 月 8 日 |
| **在 Mobile 記分卡中隱藏比較日期範圍** | 使用 Mobile 記分卡，您可以切換&#x200B;**[!UICONTROL 包括比較日期]**&#x200B;設定以檢視或隱藏比較日期。 | 不適用 | 2023 年 2 月 8 日 |
| **Workspace 中的行事曆更新** | <ul><li>錨點面板日期：您可以使日期範圍元件相對於面板行事曆。 [了解更多](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>行事曆樣式更新：整個 UI 的行事曆樣式已升級，展現更為一致易用的工作流程。</li><li>行事曆公式更新：如果您使用相對日期，所有行事曆公式將反映面板日期範圍的開始。 [了解更多](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | 不適用 | 2023 年 2 月 8 日 |
| **面板日期範圍更新** | 在工作區中，我們新增了下列改良功能：<ul><li>從2月版開始，元件和資料預覽將以面板日期範圍為基礎，而非最近90天。 </li><li>左側邊欄中列出的所有元件都可依據面板日期範圍使用。</li><li>區段和計算量度產生器中的所有日期預覽都將根據面板日期範圍（除非從沒有相關聯面板的元件管理員存取，否則仍會根據過去90天進行）。</li><li>任何資料預覽都會根據面板日期範圍顯示資料或元件。</li></ul> | 不適用 | 2023 年 2 月 8 日 |
| **Adobe Analytics Source Connector 串流傳輸的行/列篩選** | Adobe Experience Platform 中的 Analytics Source Connector 現在允許篩選 Analytics 資料；這類資料是用來在[即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)中填入設定檔。列層級篩選有助減少與設定檔有關聯的事件數量。 行層級篩選有助減少事件本身的豐富度，進而讓您可最佳化設定檔權利的使用。這項篩選僅適用於傳送至即時客戶設定檔和[身份服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant)的資料。**篩選不會影響傳送到資料湖的資料；這類資料是供 Customer Journey Analytics** 等應用程式使用。 [了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant#filtering-for-profile) | 不適用 | 改期至2023年3月29日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

-302282；AN-303127；AN-303541；AN-303550；AN-305282；AN-306504；AN-307351；AN-307496；AN-307530；AN-307947；AN-308497；AN-；AN-308610；AN-308777；AN-308994；AN-309143；AN-309404；AN-309414；AN-309445；AN-309575；AN-309630；AN-309658；AN-309690；AN-309742；AN-309861；AN-309967；AN-309973；AN-310059；AN-310132；AN-310168；AN-310238；AN-310241；AN-310301；AN-310318；AN-310324；AN-310335；AN-310338；AN-310460；AN-310500；AN-310684；AN-310690；AN-311010；AN-311022；AN-311043；AN-311125；AN-311250；AN-311370；AN-311458；

## 給 Adobe Analytics 管理員的重要通知

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **遵循 Google 用戶端提示更新裝置查詢** | 2023 年 2 月 17 日 | **計劃於 2023 年 2 月 16 日使用的用戶端提示已延後，以便進一步確保使用提示的裝置查詢品質。 我們不久便會宣布新的推出日期。** [了解更多](/help/technotes/client-hints.md) |
| **Analytics 來源連接器可用性** | 2023 年 2 月 15 日 | 2023 年 2 月 28 日，位於加拿大的新 Adobe Experience Platform 資料中心將提供 Analytics 來源連接器。 |
| **自動移轉到分類集架構** | 2023 年 2 月 8 日 | 在接下來的幾個月裡，Adobe 計畫將所有組織的所有分類移轉到最新的分類架構。最後一批移轉的客戶估計會在 2023 年 5 月進行。客戶無須採取行動，也預計不會出現停機時間。這種新架構有很多好處，包括：<ul><li>大幅縮短處理時間 (72 小時 → 24 小時)</li><li>使用[分類集](/help/components/classifications/sets/overview.md)使用者介面的能力</li><li>未來透過[用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=zh-Hant)在 Adobe Experience Platform 中使用分類資料的選項</li></ul>請注意以下變更可能會影響您組織的工作流程：<ul><li>使用瀏覽器或 FTP 匯入時，一定要啟用「[!UICONTROL 衝突時覆寫]」。</li><li>使用瀏覽器或 FTP 匯入時，不再支援匯入後立即匯出的選項。</li><li>Analytics 2.0 API `GetDimensions`端點現在回傳用於分類的字串識別碼，而不是數值識別碼。還是可以使用數值識別碼，但 Adobe 建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。</li></ul>如果您想為您的組織擬定更具體的移轉計畫，或者對此移轉有疑問/疑慮，請聯繫 Adobe 客戶服務。[了解更多](/help/components/classifications/sets/overview.md) |

{style=&quot;table-layout:auto&quot;}

## 生命週期結束 (EOL) 重要通知

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **一些 Reports &amp; Analytics 和 Report Builder 排程功能的 EOL** | 2023 年 2 月 9 日 | 以下排程功能已於 2023 年 1 月 31 日停用：<ul><li>Report Builder 中每小時任務的「在發生 x 次後結束」選項</li><li>在 Reports and Analytics 中新報告排程和下載資料擷取的能力</li></ul><p>**注意**：我們原本在 2022 年 4 月終止了這些功能，但收回了變更。我們也發送了通知，告知暫時恢復這些功能，並將於 2023 年 1 月 31 日再度終止。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，發佈清單預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有發佈清單，來傳送或排程 Analysis Workspace 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

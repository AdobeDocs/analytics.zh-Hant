---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ca99382a39644dc422baaf7dbd5c4d95942455af
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 88%

---

# Adobe Analytics 目前的版本注意事項 (2023 年 3 月)

**上次更新日期**：2023 年 3 月 10 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace 中的資料字典** | 資料字典可幫助使用者和管理員追蹤、管理並深入了解在其 Analytics 環境中的元件 (維度、量度)。[了解更多](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 15 日 | 2023 年 3 月 29 日 |
| **行動儀表板中的資料故事** | 資料故事可讓您將多個可自訂的詳細資料檢視加入到行動計分卡專案的圖磚中。使用資料故事可深入了解關鍵驅動因素、相關量度以及客戶歷程中的不同步驟。您可以輕鬆滑動這些檢視以了解關鍵量度背後的整個故事。[了解更多](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | 不適用 | 2023 年 3 月 8 日 |
| **已排程專案的到期日** | 無論排程頻率如何，您都可以將已排程專案的最長到期日設定為將近一年。 | 不適用 | 2023 年 3 月 8 日 |
| **專案連結共用 (不需登入)** - 僅限 Private beta 存取權 | <p>您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。您可以與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用專案連結。[了解更多](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>若要加入 Private beta，請聯絡您的 Adobe 客戶團隊。</p> | 2023 年 3 月 15 日 (Private beta) | 2023 年 4 月 |
| **面板日期範圍更新** | 在 Workspace 中，我們新增了以下改善：<ul><li>從2月版開始，維度項目和資料預覽皆以面板日期範圍為基礎，而非最近90天。 </li><li>列出的所有維度項目都以面板日期範圍內的資料為基礎。 如果維度項目的資料超出日期範圍，您可以在清單底部顯示日期範圍以外的其他資料。</li><li>沒有資料的Dimension可顯示在左側邊欄中。 按一下顯示更多選項，檢視含有面板日期範圍以外資料的維度項目。</li><li>區段和計算量度產生器中的資料預覽是根據面板日期範圍，除非從元件管理員存取，元件管理員沒有相關聯的面板，且仍以過去90天為基礎。</li><li>資料預覽會根據面板日期範圍顯示資料或元件。</li></ul> | 不適用 | 2023 年 2 月 8 日 |

## Adobe Analytics 中的修正

AN-308177; AN-308727; AN-308846; AN-309591; AN-310614; AN-311544; AN-311570; AN-311665; AN-311948; AN-312108; AN-312114; AN-312142; AN-312143; AN-312389; AN-312391; AN-312431; AN-312453; AN-312454; AN-312458; AN-312503; AN-312533; AN-312682; AN-312698; AN-312714; AN-312738; AN-312807; AN-312829; AN-312849; AN-312875; AN-312980; AN-312997; AN-313059; AN-313077; AN-313110; AN-313195; AN-313196; AN-313258; AN-313554; AN-313580; AN-313702; AN-313820; AN-313844; AN-313859; AN-313879; AN-314273

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **遵循 Google 用戶端提示更新裝置查詢** | 2023 年 2 月 27 日 | 計劃於 2023 年 2 月 16 日使用的用戶端提示已延後，以便進一步確保使用提示的裝置查詢品質。我們在 2023 年 2 月 27 日進行了第一階段的版本以支援用戶端提示。第二階段也是最後階段的版本已於 2023 年 3 月 2 日星期四完成。[了解更多](/help/technotes/client-hints.md) |
| **Analytics 來源連接器可用性** | 2023 年 2 月 15 日 | 2023 年 2 月 28 日，位於加拿大的新 Adobe Experience Platform 資料中心將提供 Analytics 來源連接器。 |
| **自動移轉到分類集架構** | 2023 年 2 月 8 日 | 在接下來的幾個月裡，Adobe 計畫將所有組織的所有分類移轉到最新的分類架構。最後一批移轉的客戶估計會在 2023 年 5 月進行。客戶無須採取行動，也預計不會出現停機時間。這種新架構有很多好處，包括：<ul><li>大幅縮短處理時間 (72 小時 → 24 小時)</li><li>使用[分類集](/help/components/classifications/sets/overview.md)使用者介面的能力</li><li>未來透過[用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=zh-Hant)在 Adobe Experience Platform 中使用分類資料的選項</li></ul>請注意以下變更可能會影響您組織的工作流程：<ul><li>使用瀏覽器或 FTP 匯入時，一定要啟用「[!UICONTROL 衝突時覆寫]」。</li><li>使用瀏覽器或 FTP 匯入時，不再支援匯入後立即匯出的選項。</li><li>Analytics 2.0 API `GetDimensions`端點現在回傳用於分類的字串識別碼，而不是數值識別碼。還是可以使用數值識別碼，但 Adobe 建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。</li></ul>如果您想為您的組織擬定更具體的移轉計畫，或者對此移轉有疑問/疑慮，請聯繫 Adobe 客戶服務。[了解更多](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。在&#x200B;**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報表將自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **[!UICONTROL 人員]量度生命週期結束** | 2023 年 3 月 9 日 | 隨著 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html) 淘汰不用，Device Co-op 相關量度已不再相關。2023年5月8日，我們將 [!UICONTROL 人員] 量度。 屆時，我們會將其資料重新導向至[!UICONTROL 不重複訪客]量度，以防止專案、區段和計算量度中斷。<p>**請注意**：與[[!UICONTROL 跨裝置分析相連結的人員]量度](/help/components/metrics/people.md)不受本公告影響。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，[!UICONTROL 發佈清單]預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。 |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

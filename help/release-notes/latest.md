---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6e6fcca0c2fa1fd1ee433c7d1b9727c058bb711e
workflow-type: tm+mt
source-wordcount: '1062'
ht-degree: 58%

---

# Adobe Analytics 目前的版本注意事項 (2023 年 3 月)

**上次更新日期**：2023 年 3 月 7 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace中的資料字典** | 資料字典可協助使用者和管理員追蹤、管理Analytics環境中的元件（維度、量度），並使其更清楚明瞭。 [了解更多](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 15 日 | 2023年3月22日 |
| **行動控制面板中的資料動態** | 資料動態可讓您將多個可自訂的詳細資料檢視新增至行動計分卡專案中的圖磚。 使用資料故事來深入了解關鍵驅動因素、相關量度，以及客戶歷程中的不同步驟。 您可以輕鬆輕掃這些檢視，了解關鍵量度背後的整個故事。 [了解更多](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | 不適用 | 2023年3月8日 |
| **排程專案的到期日** | 無論排程頻率為何，您都可以將已排程專案的到期日上限設定為最多一年。 | 不適用 | 2023年3月8日 |
| **專案的連結共用（不需登入）**  — 僅限私人測試版存取 | <p>您現在可以與無法存取Analysis Workspace的使用者共用Adobe Analytics專案的唯讀連結。 您可以與組織外部人員，或組織內未布建Adobe Analytics的人員共用專案連結。 [了解更多](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>若要加入私人測試版，請連絡您的Adobe客戶團隊。</p> | 2023年3月15日（非公開測試版） | 2023 年 4 月 |

## Adobe Analytics 中的修正

AN-308177;AN-308727;AN-308846;AN-309591;AN-310614;AN-311544;AN-311570;AN-311665;AN-311948;AN-312108;AN-312114;AN-312142;AN-312143;AN-312389;AN-312391;AN-312431;AN-312453;AN-312454;AN-312458;AN-312503;AN-312533;AN-312682;AN-312698;AN-312714;AN-312738;AN-312807;AN-312829;AN-312849;AN-312875;AN-312980;AN-312997;AN-313059;AN-313077;AN-313110;AN-313195;AN-313196;AN-313258;AN-313554;AN-313580;AN-313702;AN-313820;AN-313844;AN-313859;AN-313879;AN-314273

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **遵循 Google 用戶端提示更新裝置查詢** | 2023 年 2 月 27 日 | 計劃於 2023 年 2 月 16 日使用的用戶端提示已延後，以便進一步確保使用提示的裝置查詢品質。 我們於2023年2月27日開始了第一階段的發佈，以支援客戶提示。 發行的第二階段也是最後階段已於2023年3月2日星期四完成。 [了解更多](/help/technotes/client-hints.md) |
| **Analytics 來源連接器可用性** | 2023 年 2 月 15 日 | 2023年2月28日，位於加拿大的新Adobe Experience Platform資料中心推出Analytics Source Connector。 |
| **自動移轉到分類集架構** | 2023 年 2 月 8 日 | 在接下來的幾個月裡，Adobe 計畫將所有組織的所有分類移轉到最新的分類架構。最後一批移轉的客戶估計會在 2023 年 5 月進行。客戶無須採取行動，也預計不會出現停機時間。這種新架構有很多好處，包括：<ul><li>大幅縮短處理時間 (72 小時 → 24 小時)</li><li>使用[分類集](/help/components/classifications/sets/overview.md)使用者介面的能力</li><li>未來透過[用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=zh-Hant)在 Adobe Experience Platform 中使用分類資料的選項</li></ul>請注意以下變更可能會影響您組織的工作流程：<ul><li>使用瀏覽器或 FTP 匯入時，一定要啟用「[!UICONTROL 衝突時覆寫]」。</li><li>使用瀏覽器或 FTP 匯入時，不再支援匯入後立即匯出的選項。</li><li>Analytics 2.0 API `GetDimensions`端點現在回傳用於分類的字串識別碼，而不是數值識別碼。還是可以使用數值識別碼，但 Adobe 建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。</li></ul>如果您想為您的組織擬定更具體的移轉計畫，或者對此移轉有疑問/疑慮，請聯繫 Adobe 客戶服務。[了解更多](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>我們將於2023年12月31日終止許多相關Reports &amp; Analytics功能，包括但不限於：排程報表、資料擷取和DL報表。 2023年12月31日後，將不再傳送任何排程報表。 在 **2023年4月**，則任何排程在2023年12月31日後過期的報表都會自動更新，並還原為在2023年12月31日過期。 此外，您無法再排程2023年12月31日以後的報表。 |
| **終止 [!UICONTROL 人員] 量度** | 2023 年 2 月 28 日 | 隨著 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html)，則Device Co-op相關人員量度不再相關。 在不久的將來（未定日期），我們將移除此項 [!UICONTROL 人員] 量度。 此時，我們會將其資料重新導向至 [!UICONTROL 不重複訪客] 量度來防止專案、區段和計算量度中斷。<p>**附註**:此 [[!UICONTROL 人員] 系結至跨裝置分析的量度](/help/components/metrics/people.md) 不受本公告的影響。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為「Reports &amp; Analytics」終止服務的一部分， [!UICONTROL 發佈清單] 將於 **2023年12月**. 您將無法建立新內容或存取現有內容 [!UICONTROL 發佈清單] 傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
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

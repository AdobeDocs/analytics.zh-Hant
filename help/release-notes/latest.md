---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f4cf651e07da27c416fc02b184b80bc07756eb33
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 81%

---

# Adobe Analytics 目前的版本注意事項 (2023 年 4 月)

**上次更新日期**：2023 年 4 月 12 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics Source Connector 串流傳輸的行/列篩選** | Adobe Experience Platform 中的 Analytics Source Connector 現在允許篩選 Analytics 資料；這類資料是用來在[即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)中填入設定檔。列層級篩選有助減少與設定檔有關聯的事件數量。行層級篩選有助減少事件本身的豐富度，進而讓您可最佳化設定檔權利的使用。這項篩選僅適用於傳送至即時客戶設定檔和[身份服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant)的資料。**篩選不會影響傳送到資料湖的資料；這類資料是供 Customer Journey Analytics** 等應用程式使用。[了解更多](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant#filtering-for-profile) | 不適用 | 2023 年 3 月 29 日 |
| **Web SDK 部分支援 Activity Map** | 從 Web SDK 2.15.0 版本開始，我們開始在啟用連結追蹤時填入 Activity Map 資料。如果 Web SDK 已啟用連結追蹤且 Analytics 已設定 Activity Map，這允許 Web SDK 使用者取得 Activity Map 報告。<p>目前，如果 Web SDK 啟用連結追蹤，在客戶從一個頁面導覽到下一個頁面時會傳送連結事件。這與 AppMeasurement 的運作方式不同，可能會導致傳送額外的計費點擊給 Adobe。在[此處](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html)和[此處](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)了解更多資訊 | 不適用 | 2023 年 3 月 31 日 |
| **Experience Edge的IP模糊化** | Experience Edge支援直接傳送至Adobe Experience Platform之資料的IP模糊化功能。 如此可讓直接將資料傳送至Platform以用於CJA或其他Platform解決方案的客戶受益。 IP模糊化是在資料流層級設定。 支援移除最後八位元或整個IP位址。<p>**附註**:模糊化不適用於傳送至Adobe Analytics的資料。 Analytics會繼續取得完整IP。 IP處理會繼續在Analytics中個別執行。 未來我們計畫允許將Analytics資料模糊化至Edge。 | 不適用 | AEP 2023年4月26日發行 |
| **Analysis Workspace 中的資料字典** | 資料字典可幫助使用者和管理員追蹤、管理並深入了解在其 Analytics 環境中的元件 (維度、量度)。[了解更多](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 15 日 | 2023 年 3 月 29 日 |
| **專案連結共用 (不需登入)** - 僅限 Private beta 存取權 | <p>您現在可以與無 Adobe Analytics 存取權的人員共用 Analysis Workspace 專案的唯讀連結。您可以與組織外的人員或組織內未佈建 Adobe Analytics 的人員共用專案連結。[了解更多](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>若要加入 Private beta，請聯絡您的 Adobe 客戶團隊。</p> | 2023 年 4 月 26 日 | 2023 年 6 月 |
| 2個適用於Adobe Analytics 2.0 API的新端點指南 | <ul><li>[AnalyticsDimensionAPI](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[Analytics量度API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> | 不適用 | 2023 年 4 月 10 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正資料摘要中Operating System.tsv查閱檔案的問題。
* 修正「Reports &amp; Analytics」與「工作區」之間量度值不同的問題(AN-315965)。
* 修正無法匯入部分分類的問題。 (AN-315854)
* 修正Analytics API 1.4的問題。 (AN-316475)
* 修正部分客戶無法透過「Report Builder」和「Report &amp; Analytics」獲得「頁面」維度分類的問題。 (AN-314445)
* 修正無法傳輸警報的問題。 (AN-306457)

### 其他修正

AN-288373;AN-305144;AN-309023;AN-310466;AN-311686;AN-311705;AN-312018;AN-312105;AN-312116;AN-312191;AN-312502;AN-312737;AN-312854;AN-312991;AN-313253;AN-313275;AN-313278;AN-313282;AN-313365;AN-313390;AN-313547;AN-313549;AN-313818;AN-313986;AN-314080;AN-314248;AN-314251;AN-314262;AN-314300;AN-314309;AN-314448;AN-314643;AN-314564;AN-314645;AN-314705;AN-314761;AN-314831;AN-314919;AN-314948;AN-315032;AN-315115;AN-315154;AN-315158;AN-315321;AN-315375;AN-315379;AN-315392;AN-315407;AN-315427;AN-315582;AN-315591;AN-315699;AN-315700;AN-315704;AN-315705;AN-315777;AN-315923;AN-316237;AN-316243;AN-316324;AN-316415;AN-316474;AN-316493;AN-316596;AN-316864;

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **裝置查詢流程現在使用協力廠商進行所有裝置查詢** | 2023 年 3 月 3 日 | 2023 年 3 月 2 日，我們推出了用戶端提示支援，更新了裝置查詢流程以使用協力廠商進行所有裝置查詢。先前，協力廠商只用於進行行動裝置查詢。而在此次推出的內容中，部分桌面作業系統誤標記了「Mobile」文字 (例如，「Mobile OS X 10.15.7」而不是「OS X 10.15.7」)。<p>在 Adobe 4 月版中，我們將更正這些名稱。Analytics 和 CJA 報告將追溯更新，因為它們的報告是根據記錄為事件資料的 ID 來查詢作業系統名稱。一旦 ID 對應的查詢值更新，所有的報告都會修正，包括歷史資料。對於[!UICONTROL 資料摘要]客戶，如果您在報告時使用類似的查詢程序，則變更會具有追溯力。但是，如果您將作業系統值儲存在事件資料中，則只會更新未來的報告。如需詳細資料，請參閱[作業系統](/help/components/dimensions/operating-systems.md)。 |
| **遵循 Google 用戶端提示更新裝置查詢** | 2023 年 2 月 27 日 | 計劃於 2023 年 2 月 16 日使用的用戶端提示已延後，以便進一步確保使用提示的裝置查詢品質。我們在 2023 年 2 月 27 日進行了第一階段的版本以支援用戶端提示。第二階段也是最後階段的版本已於 2023 年 3 月 2 日星期四完成。[了解更多](/help/technotes/client-hints.md) |
| **自動移轉到分類集架構** | 2023 年 2 月 8 日 | 在接下來的幾個月裡，Adobe 計畫將所有組織的所有分類移轉到最新的分類架構。最後一批移轉的客戶估計會在 2023 年 5 月進行。客戶無須採取行動，也預計不會出現停機時間。這種新架構有很多好處，包括：<ul><li>大幅縮短處理時間 (72 小時 → 24 小時)</li><li>使用[分類集](/help/components/classifications/sets/overview.md)使用者介面的能力</li><li>未來透過[用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=zh-Hant)在 Adobe Experience Platform 中使用分類資料的選項</li></ul>請注意以下變更可能會影響您組織的工作流程：<ul><li>使用瀏覽器或 FTP 匯入時，一定要啟用「[!UICONTROL 衝突時覆寫]」。</li><li>使用瀏覽器或 FTP 匯入時，不再支援匯入後立即匯出的選項。</li><li>Analytics 2.0 API `GetDimensions`端點現在回傳用於分類的字串識別碼，而不是數值識別碼。還是可以使用數值識別碼，但 Adobe 建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。</li></ul>如果您想為您的組織擬定更具體的移轉計畫，或者對此移轉有疑問/疑慮，請聯繫 Adobe 客戶服務。[了解更多](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **日本功能型手機追蹤服務終止** | 2023 年 3 月 21 日 | 僅適用於日本客戶：在 **2023年5月底**，日本功能電話追蹤服務(mod_ktrack)將停止提供。 對於所造成的不便，我們深表歉意，但請您卸載或停用安裝在 Apache 伺服器上的模組。請參閱[本文件](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf)的第 27 和 28 頁深入了解。 |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。在&#x200B;**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報表將自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **[!UICONTROL 人員]量度生命週期結束** | 2023 年 3 月 9 日 | 隨著 [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html) 淘汰不用，Device Co-op 相關的人員量度已不再相關。2023 年 5 月 8 日，我們將移除[!UICONTROL 人員]量度。屆時，我們會將其資料重新導向至[!UICONTROL 不重複訪客]量度，以防止專案、區段和計算量度中斷。<p>**請注意**：與[[!UICONTROL 跨裝置分析相連結的人員]量度](/help/components/metrics/people.md)不受本公告影響。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，[!UICONTROL 發佈清單]預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7c66414129e262954e5521a28b878424099ac6ad
workflow-type: tm+mt
source-wordcount: '1426'
ht-degree: 98%

---

# 目前的 Adobe Analytics 發行說明 (2022 年 10/11 月)

**上次更新日期**：2022 年 10 月 28 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## Adobe Analytics 中的新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **[!UICONTROL 關鍵量度摘要]** 視覺化 | [!UICONTROL 關鍵量度摘要]視覺化可讓您查看一項重要量度在單一時間範圍內的趨勢分析。也能讓您比較兩個時間範圍內的量度成效。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=zh-Hant) | 2022 年 10 月 5 日 | 2023 年 10 月 19 日 |
| **不區分大小寫的多值變數** | 若為不區分大小寫的多值變數，則儲存在 `mvvar1 - mvvar3` 和 `post_mvvar1 - post_mvvar3` 資料摘要中的「 」不再自動變成小寫。 相反的，資料摘要 (以及透過 Analytics Source Connector 傳遞到 Adobe Experience Platform 和 CJA 的資料) 將反映從頁面傳入的原始大小寫。 | 不適用 | 2022 年 10 月 24 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修正最近 MacOS 版本誤命名為「Macintosh」的問題。透過此修正，作業系統維度將開始使用「MacOS」版本編號，從 MacOS 11 開始。(AN-301834)
* 已修正 Report Builder 中「固定日期」日期範圍的問題。(AN-303684)
* 已修正無法載入資料摘要 UI 的問題。(AN-303803、AN-303784)

### 其他修正

-295574；AN-296354；AN-297143；AN-299501；AN-301755；AN-302054；AN-302304；AN-302631；AN-302811；AN-303090；AN-303372；AN-；AN-303428；AN-303429；AN-303432；AN-303434；AN-303437；AN-303438；AN-303519；AN-303610；AN-303656；AN-303659；；AN-303663；AN-303664；AN-303818；AN-303823；AN-303837；AN-304036；AN-304195；AN-304321；AN-304325；AN-304339；AN-304356；AN-304435；AN-304457；AN-304509；AN-304519；AN-304534

## 給 Adobe Analytics 管理員的重要通知

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **遵循 Google 用戶端提示更新裝置查詢** | 2022 年 10 月 14 日 | 原先計劃於 2022 年 10 月 26 日在裝置查找中使用的用戶端提示已延遲至 **2023 年 1 月**。 <p> <p>自 2022 年 10 月起，即可使用 Web SDK 或 AppMeasurement JavaScript 庫收集用戶端提示。但直到 2023 年 1 月，用戶端提示才會被納入裝置查找中。在那一天，在為來自 Chromium 瀏覽器 (例如 Google Chrome 和 Microsoft Edge) 的點擊取得某些裝置資訊時，除了使用者代理程式之外，Adobe 將開始使用用戶端提示。這是為了因應 Google 計劃逐漸減少從使用者代理字串呈現的資訊，以取代透過用戶端提示傳遞的資料。 <p> <p>作為此變更的一部分，Adobe 將使用 Device Atlas 進行所有和使用者代理程式相關的裝置查找。[了解更多](/help/technotes/client-hints.md) |
| **預設登陸頁面** | 2022 年 9 月 29 日 | 今年初推出的[新登陸頁面](/help/analyze/landing.md)將在 **2023 年 1 月**&#x200B;成為所有使用者的預設體驗。目前頁面將被淘汰，將要求所有人都使用新體驗。 |
| **[!UICONTROL 異常偵測] 自動執行條件** | 2022 年 9 月 29 日 | 現在，[!UICONTROL 異常偵測]會在時間序列自由表格的所有欄上自動執行。為確保資料可用於分析且專案可更快地載入，Adobe 將變更異常偵測自動執行的方式。自 **2022 年 10 月 26 日**&#x200B;開始，[!UICONTROL 異常偵測] 將僅在表格的第一個量度欄上自動執行。如果需要，您可以配置欄設定，以對其他欄執行異常偵測。 |
| **新 NetAcuity 電信業者資料庫的更新** | 2022 年 9 月 26 日 | 這項更新原計劃於 2022 年 10 月 5 日推出，現已推遲到 **2023 年 1 月**。儲存在 Adobe Analytics Data Warehouse 和 Analytics 資料摘要的 `carrier` 欄位中的電信業者相關資訊將會變更。在過去，該欄中的資料格式一直是 `<domain>:<ISP>`。Adobe 已維護一份內部查詢表，以便將這些 `<domain>:<ISP>` 值對應到電信業者名稱，以供在 Adobe Analytics 報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、LiveStream 等) 中進行報告之用。此查詢檔案 (`carrier.tsv`) 也隨附資料摘要，讓您可以使用相同的對應。<p>此更新使用來自 NetAcuity 的較準確電信業者資料庫，藉以強化我們的電信業者對應。未來，資料摘要中電信業者欄的資料格式將會變更。它將包含電信業者名稱，而不是 `<domain>:<ISP>`。Adobe 將繼續使用查詢表，以盡可能保持與過去報告的連續性。Adobe 套用查詢的報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流等) 將受益於較準確的對應。Adobe 採用新資料庫時，某些對應 (特別是國際網域和 ISP 的對應) 將比其他對應發生更多變化。資料摘要電信業者查詢檔案 (`carrier.tsv`) 將維持舊的對應，同時加入新的對應。<p>Analytics 來源連接器目前不會對應電信業者欄位，因此 Experience Platform、CJA 等項目中目前不提供電信業者報告。因此，使用新電信業者資料庫將不會影響 Experience Platform 中以 Analytics 來源連接器所提供之資料為依據的任何內容。 |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 26 日 | 我們的 IP 查詢供應商 Digital Element 即將升級到新改良的資料集 (NetAcuity Pulse)，以便用於 IP 對地理位置的對應。Adobe Analytics 將在 **2023 年 1 月** (原計劃於 2022 年 10 月) 採用此新的資料集。新資料庫將會比舊版更準確。在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p>所有 Adobe Analytics 工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流、資料摘要等) 都將會自動利用新改良的對應。資料摘要中的資料格式不會改變。透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |
| **暫停 Reports &amp; Analytics 中的排程報告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，Adobe 宣布淘汰排程報告的幾個特定功能，為先前宣布的 Reports &amp; Analytics 生命週期結束做準備。這些功能包括排程新報告以及擷取新資料的能力。<p>為因應客戶要求延長以及簡化從 Reports &amp; Analytics 的轉換作業，Adobe 決定將這些功能的存取權延長到 **2023 年 1 月 31 日**。請注意，報告和資料擷取的到期窗口限制仍維持九個月；報告和資料擷取的傳送將在此期間結束時暫停，除非重新啟用排程。<p>再次強調，這些功能將在 2023 年 1 月 31 日淘汰。在此日期之前，您必須將排程報告遷移至 Adobe Analytics 中任何您可以使用的其他機制之一。如有其他問題或需要支援，請和 Adobe 客戶服務聯絡。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **暫停 Report Builder 中的排程工作** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，Adobe 在我們的效能和傳遞最佳化工作中，對 Report Builder 的排程工作推出變更。這些變更包括移除讓已排程傳遞「在 x 次發生次數後結束」的功能。為因應多位客戶要求更多時間以便探索和實施替代方案，Adobe 決定以有限的方式恢復此選項，直到 **2023 年 1 月 31 日**&#x200B;為止。<p>您可繼續排程每小時的 Report Builder 工作，並使其在最多 99 次發生次數後結束。請注意，復原作業僅適用於每小時工作；所有其他傳遞間隔 (每日、每週、每月和每年) 仍無法使用「x 次發生次數後結束」功能。請注意，此選項將於 2023 年 1 月 31 日停止使用。如有更多問題或需要支援，請聯絡 Adobe 客戶服務。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## 生命週期結束重要通知

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，發佈清單預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有發佈清單，來傳送或排程 Analysis Workspace 專案。[了解更多](/help/admin/admin/publishing-list.md) |
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

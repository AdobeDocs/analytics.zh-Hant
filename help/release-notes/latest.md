---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 74c347c72394b75cc332ae459b9cbf1f72fa033b
workflow-type: tm+mt
source-wordcount: '1205'
ht-degree: 88%

---

# 最新Adobe Analytics發行說明（2022年9月）

**上次更新日期**：2022 年 9 月 9 日

>[!NOTE]
>
>本頁面包含搶鮮版內容，且可能有所變更。

## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

## Adobe Analytics 中的新功能或更新功能

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| 工作區中的組合圖視覺效果 | 組合圖表可讓您在工作區中更輕鬆、直覺地比較量度。 [了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts.html) | 2022 年 9 月 14 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 修正分類匯入和匯出的問題。 (AN-299267)

**為個別客戶進行的修正**：

AN-288519;AN-289300;AN-297387;AN-297465;AN-297520;AN-297641;AN-298134;AN-298351;AN-298429;AN-298483;AN-298520;AN-298582;AN-298816;AN-298832;AN-298855;AN-298864;AN-299407;AN-299545;AN-299644;AN-299715

## 給 Adobe Analytics 管理員的重要通知

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **SFTP 升級** | 2022 年 9 月 9 日 | 我們先前已宣布，Adobe 會在 2022 年 9 月升級其安全檔案傳輸協定 (SFTP)，以提升檔案傳輸的安全性。我們已將此升級延後至 **2022年9月中至下旬**. 進行此變更後，將不再支援某些 SFTP 用戶端設定。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)詳述的變更。 |
| **Data Workbench 生命週期結束** | 2022 年 9 月 9 日 | Adobe 打算自&#x200B;**2023 年 12 月 31 日** 起終止 Data Workbench 的生命週期。更多詳細資訊即將公告。 |
| **遵循 Google 用戶端提示更新裝置查詢** | 2022 年 9 月 9 日 | 開始於 **2022年9月29日**，從Google Chrome和Microsoft Edge等Chromium瀏覽器衍生點擊的特定裝置資訊時，Adobe將開始使用除使用者代理以外的用戶端提示。 這是為了因應 Google 計劃逐漸減少從使用者代理字串呈現的資訊，以取代透過用戶端提示傳遞的資料。在 [此處](https://web.dev/user-agent-client-hints/) 閱讀有關用戶端提示的更多資訊。<p> 到 10 月，AppMeasurement 和 Web SDK 收集庫都將支援收集用戶端提示，並設定是否要收集高熵用戶端提示。作為此變更的一部分，Adobe 將使用 Device Atlas 進行所有與使用者代理程式相關的裝置查詢。目前 Device Atlas 僅用於行動裝置點擊。這些更新可能會導致以往從使用者代理程式衍生的裝置資訊發生細微的變化 - 特別是瀏覽器、瀏覽器類型、作業系統、作業系統類型和行動裝置。 |
| **新 NetAcuity 電信業者資料庫的更新** | 2022 年 9 月 9 日 | **自2022年10月5日起**，儲存於 `carrier` 「Adobe AnalyticsData Warehouse」和「Analytics資料摘要」中的欄位將會變更。 在過去，該欄中的資料格式一直是 `<domain>:<ISP>`。Adobe 已維護一份內部查詢表，以便將這些 `<domain>:<ISP>` 值對應到電信業者名稱，以供在 Adobe Analytics 報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流等) 中進行報告之用。此查詢檔案 (`carrier.tsv`) 也隨附資料摘要，讓您可以使用相同的對應。<p>此更新使用來自 NetAcuity 的較準確電信業者資料庫，藉以強化我們的電信業者對應。未來，資料摘要中電信業者欄的資料格式將會變更。它將包含電信業者名稱，而不是 `<domain>:<ISP>`。 Adobe 將繼續使用查詢表，以盡可能保持與過去報告的連續性。 Adobe 套用查詢的報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流等) 將受益於較準確的對應。 當我們採用新資料庫時，某些對應 (特別是國際網域和 ISP 的對應) 將比其他對應發生更多變化。 資料摘要電信業者查詢檔案 (`carrier.tsv`) 將維護舊的對應，同時加入新的對應。<p>Analytics Source Connector 目前不會對應電信業者欄位，所以目前 AEP、CJA 等項目中不提供電信業者報告。 因此，使用新電信業者資料庫將不會影響 AEP 中根據 Analytics Source Connector 所提供之資料的任何內容。 |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 9 日 | 我們的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics將採用此新資料集 **2022年10月5日**. 新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p>所有 Adobe Analytics 工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流、資料摘要等) 都將會自動利用新改良的對應。 資料摘要中的資料格式不會改變。 透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |
| **暫停 Reports &amp; Analytics 中的排程報告** | 2022 年 6 月 8 日 | 在 2022 年 4 月 21 日，我們宣布淘汰排程報告的幾個特定功能，為先前宣布的 Reports &amp; Analytics 生命週期結束做準備。這些功能包括排程新報告，以及擷取新資料的能力。<p>因應客戶要求延長以及為了順利從 Reports and Analytics 進行轉換，我們決定將這些功能的存取權延長到 **2023 年 1 月 31 日**。請注意，報告和資料擷取的到期窗口限制仍為九個月；報告和資料擷取的傳遞將在此期間結束時暫停，除非重新啟用排程。<p>再次強調，這些功能將在 2023 年 1 月 31 日淘汰。在此日期之前，您必須將排程報告遷移至 Adobe Analytics 中任何您可以使用的其他機制之一。如有其他問題或需要支援，請和 Adobe 客戶服務聯絡。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **暫停 Report Builder 中的排程工作** | 2022 年 6 月 8 日 | 在 2022 年 4 月 21 日，我們對 Report Builder 中的排程工作推出變更，這屬於我們效能和傳遞最佳化工作的一部分。這些變更包括移除讓排程傳遞「在 x 次發生次數後結束」的功能。因應多位客戶要求更多時間以便探索和實施替代方案，我們決定以有限的方式恢復此選項，直到 **2023 年 1 月 31 日**。<p>您可繼續排程每小時 Report Builder 工作，並在最多 99 次發生次數後結束。請注意，復原作業僅適用於每小時工作；所有其他傳遞間隔 (每日、每週、每月和每年) 仍無法使用「x 次發生次數後結束」功能。請注意，此選項將於 2023 年 1 月 31 日停止使用。如有更多問題或需要支援，請聯絡 Adobe 客戶服務。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 36abc6f887074a7f79e223277c21223ab1493afa
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 88%

---

# 最新 Adobe Analytics 版本注意事項 (2022 年 9 月)

**上次更新日期**：2022 年 9 月 22 日

Adobe Analytics版本可在 [連續配送模型](releases.md) 這可讓您以更具延展性、分階段的方式部署功能。 因此，這些發行說明每月會更新數次。 請定期檢查。

## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

## Adobe Analytics 中的新功能或更新功能

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| 在 Workspace 中的組合圖表視覺效果 | 組合圖表讓您更輕鬆且直覺地比較在 Workspace 內的指標。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts.html) | 2022 年 9 月 14 日 |
| AppMeasurement 2.23.0版 | AppMeasurement 現在支援高平均資訊量使用者代理程式用戶端提示的收藏集，Chromium 瀏覽器 (Google Chrome 和 Microsoft Edge) 會使用上述提示來提供裝置資訊。您可透過「標記」設定用戶端提示或使用「collectHighEntropyUserAgentHints」旗標。依預設，會關閉高平均資訊量的收藏集。 [了解更多](/help/technotes/client-hints.md) | 2022 年 9 月 23 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修正分類匯入與匯出的問題。(AN-299267)

**為個別客戶進行的修正**：

AN-288519; AN-289300; AN-297387; AN-297465; AN-297520; AN-297641; AN-298134; AN-298351; AN-298429; AN-298483; AN-298520; AN-298582; AN-298816; AN-298832; AN-298855; AN-298864; AN-299407; AN-299545; AN-299644; AN-299715

## 給 Adobe Analytics 管理員的重要通知

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **遵循 Google 用戶端提示更新裝置查詢** | 2022 年 8 月 19 日 | 自2022年10月起，Adobe將開始在從Chromium瀏覽器(例如Google Chrome和Microsoft Edge)衍生點擊的特定裝置資訊時，除使用者代理外，還使用用戶端提示。 這是為了回應Google逐步減少從使用者代理字串呈現的資訊，以取代透過用戶端提示傳遞的資料的計畫。 在 [此處](https://web.dev/user-agent-client-hints/) 閱讀有關用戶端提示的更多資訊。<p> 到10月，AppMeasurement和Web SDK收集程式庫都將支援用戶端提示的收集，以及設定是否收集到高熵用戶端提示的設定。 在此變更中，Adobe將使用Device Atlas進行與使用者代理相關的所有裝置查閱。 目前 Device Atlas 僅用於行動裝置點擊。這些更新可能會對過去衍生自使用者代理的裝置資訊進行小幅變更，具體來說是瀏覽器、瀏覽器類型、作業系統、作業系統類型和行動裝置。 [了解更多](/help/technotes/client-hints.md) |
| **SFTP 升級** | 2022 年 9 月 19 日 | Adobe 先前已宣布，Adobe 會在 2022 年 9 月升級其安全檔案傳輸協定 (SFTP) 服務，以提升檔案傳輸的安全性。Adobe 已將此升級延後到 **2022 年 9 月 20 日**。進行此變更後，即不再支援某些 SFTP 用戶端設定。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)詳述的變更。 |
| **變更 Analytics 透過 Experience Edge 對所收集之 A4T 資料的處理方式** | 2022 年 9 月 14 日 | 2022 年 3 月，Analytics 變更了對於源自 Experience Edge 之部分呼叫的處理方式，其中包含 A4T 資料。含 A4T 報告內容的點擊已經過修改，因此不會視為頁面檢視 (`t()`) 或連結追蹤 (`tl()`) 事件。此邏輯現在已更新，以包含 `propositionDisplay` 事件未如預期修改的情況。 |
| **適用於 Web SDK 中清單變數和清單屬性的自動分隔符號** | 2022 年 9 月 14 日 | 清單變數和清單屬性現在會使用報告套裝設定中指定的分隔符號，除非 XDM 中指定了分隔符號覆寫。如需詳細資訊，請參閱[清單](/help/implement/vars/page-vars/list.md)變數。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。如果您有任何疑問，請聯絡客戶服務代表以取得 Data Workbench 的替代解決方案。 |
| **新 NetAcuity 電信業者資料庫的更新** | 2022 年 9 月 14 日 | **從 2022 年 10 月 5 日開始**，儲存在 Adobe Analytics Data Warehouse 和 Analytics Data Feeds `carrier` 欄位中的電信業者相關資訊將會變更。 在過去，該欄中的資料格式一直是 `<domain>:<ISP>`。Adobe 已維護一份內部查詢表，以便將這些 `<domain>:<ISP>` 值對應到電信業者名稱，以供在 Adobe Analytics 報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、LiveStream 等) 中進行報告之用。此查詢檔案 (`carrier.tsv`) 也隨附資料摘要，讓您可以使用相同的對應。<p>此更新使用來自 NetAcuity 的較準確電信業者資料庫，藉以強化我們的電信業者對應。未來，資料摘要中電信業者欄的資料格式將會變更。它將包含電信業者名稱，而不是 `<domain>:<ISP>`。 Adobe 將繼續使用查詢表，以盡可能保持與過去報告的連續性。 Adobe 套用查詢的報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流等) 將受益於較準確的對應。 Adobe 採用新資料庫時，某些對應 (特別是國際網域和 ISP 的對應) 將比其他對應發生更多變化。資料摘要電信業者查詢檔案 (`carrier.tsv`) 將維持舊的對應，同時加入新的對應。<p>Analytics 來源連接器目前不會對應電信業者欄位，因此 Experience Platform、CJA 等項目中目前不提供電信業者報告。因此，使用新電信業者資料庫將不會影響 Experience Platform 中以 Analytics 來源連接器所提供之資料為依據的任何內容。 |
| **已改良 IP 對地理位置的對應** | 2022 年 9 月 14 日 | 我們的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics 將在 **2022 年 10 月 5 日**&#x200B;採用此新的資料集。新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p>所有 Adobe Analytics 工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流、資料摘要等) 都將會自動利用新改良的對應。 資料摘要中的資料格式不會改變。 透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |
| **暫停 Reports &amp; Analytics 中的排程報告** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，Adobe 宣布淘汰排程報告的幾個特定功能，為先前宣布的 Reports &amp; Analytics 生命週期結束做準備。這些功能包括排程新報告以及擷取新資料的能力。<p>為因應客戶要求延長以及簡化從 Reports &amp; Analytics 的轉換作業，Adobe 決定將這些功能的存取權延長到 **2023 年 1 月 31 日**。請注意，報告和資料擷取的到期窗口限制仍維持九個月；報告和資料擷取的傳送將在此期間結束時暫停，除非重新啟用排程。<p>再次強調，這些功能將在 2023 年 1 月 31 日淘汰。在此日期之前，您必須將排程報告遷移至 Adobe Analytics 中任何您可以使用的其他機制之一。如有其他問題或需要支援，請和 Adobe 客戶服務聯絡。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **暫停 Report Builder 中的排程工作** | 2022 年 6 月 8 日 | 2022 年 4 月 21 日，Adobe 在我們的效能和傳遞最佳化工作中，對 Report Builder 的排程工作推出變更。這些變更包括移除讓已排程傳遞「在 x 次發生次數後結束」的功能。為因應多位客戶要求更多時間以便探索和實施替代方案，Adobe 決定以有限的方式恢復此選項，直到 **2023 年 1 月 31 日**&#x200B;為止。<p>您可繼續排程每小時的 Report Builder 工作，並使其在最多 99 次發生次數後結束。請注意，復原作業僅適用於每小時工作；所有其他傳遞間隔 (每日、每週、每月和每年) 仍無法使用「x 次發生次數後結束」功能。請注意，此選項將於 2023 年 1 月 31 日停止使用。如有更多問題或需要支援，請聯絡 Adobe 客戶服務。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。

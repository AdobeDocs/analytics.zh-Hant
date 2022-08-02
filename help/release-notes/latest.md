---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 100%

---

# 最新 Adobe Analytics 發行說明 (2022 年 7 月)

**上次更新日期**：2022 年 7 月 13 日

## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

## Adobe Analytics 新功能

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| XDM 中用於 Edge 集合的銷售變數支援 | 讓客戶透過 Experience Edge/Web SDK 收集資料，以使用 XDM 來指定銷售變數 (eVar) 的各個值。 [了解更多](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar-merchandising.html?lang=zh-Hant) | 2022 年 6 月 29 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修正一些區段轉換錯誤。 (AN-291262、AN-294092)

**為個別客戶進行的修正**：

AN-280192；AN-281628；AN-287022；AN-287104；AN-287876；AN-288802；AN-288457；AN-288779；AN-288799；AN-289198；AN-289852；AN-289931；AN-290162；AN-290213；AN-291059；AN-291090；AN-291270；AN-294091；AN-294135；AN-294152；AN-294158；AN-294285；AN-294317；AN-294404；AN-294531；AN-294769；AN-294984；AN-295172；AN-295211；AN-295224；AN-295413；AN-295440；AN-295465；AN-295499；AN-295516；

## 給 Adobe Analytics 管理員的重要通知

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **系統產生電子郵件的新網域** | 2022 年 7 月 13 日 | 在 **2022 年 5 月 18 日**，Adobe 已將來自工作區專案、警示和超額警示之電子郵件的寄件者網域從 `noreply@omniture.com` 變更為 `noreply@adobe.com`。 如果您的組織僅允許特定寄件者，則將此新電子郵件新增到您的允許清單中。 |
| **新 NetAcuity 電信業者資料庫的更新** | 2022 年 7 月 11 日 | **從 2022 年 10 月開始**，儲存在 Adobe Analytics Data Warehouse 和 Analytics 資料摘要中的 `carrier` 欄位中的電信業者相關資訊將會變更。 在過去，該欄中的資料格式一直是 `<domain>:<ISP>`。 Adobe 已維護內部查詢表，以便將這些 `<domain>:<ISP>` 值對應到電信業者名稱，其目的是為了在 Adobe Analytics 報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流等) 中進行報告 查詢檔案 (carrier.tsv) 也隨附資料摘要，以便資料摘要客戶可使用相同的對應。<p>此更新藉由使用 NetAcuity 提供的較準確的電信業者資料庫來強化我們的電信業者對應。 未來，資料摘要中電信業者欄的資料格式將會變更。 它將包含電信業者名稱，而不是 `<domain>:<ISP>`。 Adobe 將繼續使用查詢表，以盡可能保持與過去報告的連續性。 Adobe 套用查詢的報告工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流等) 將受益於較準確的對應。 當我們採用新資料庫時，某些對應 (特別是國際網域和 ISP 的對應) 將比其他對應發生更多變化。 資料摘要電信業者查詢表 (carrier.tsv) 將維護舊的對應，並加入新的對應。<p>Analytics Source Connector 目前不會對應電信業者欄位，所以目前 AEP、CJA 等項目中不提供電信業者報告。 因此，使用新電信業者資料庫將不會影響 AEP 中根據 Analytics Source Connector 所提供之資料的任何內容。 |
| **已改良 IP 對地理位置的對應** | 2022 年 7 月 11 日 | 我們的 IP 查詢供應商 Digital Element 正升級到新改良的資料集 (NetAcuity Pulse) 以便用於 IP 對地理位置的對應。 Adobe Analytics 將在 **2022 年 10 月**&#x200B;的時間範圍內採用這個新資料集。 新資料庫將會比舊版更準確。 在採用新資料庫後，某些 IP 對地理位置的對應將會變更/改良。<p>所有 Adobe Analytics 工具 (Analysis Workspace、Reports &amp; Analytics、報告 API、Data Warehouse、直播串流、資料摘要等) 都將會自動利用新改良的對應。 資料摘要中的資料格式不會改變。 透過 Analytics Source Connector 提供的 CJA 資料也將自動利用新的對應。 |
| **暫停 Reports &amp; Analytics 中的排程報告** | 2022 年 6 月 8 日 | 在 2022 年 4 月 21 日，我們宣布淘汰排程報告的幾個特定功能，為先前宣布的 Reports &amp; Analytics 生命週期結束做準備。這些功能包括排程新報告，以及擷取新資料的能力。<p>因應客戶要求延長以及為了順利從 Reports and Analytics 進行轉換，我們決定將這些功能的存取權延長到 **2023 年 1 月 31 日**。請注意，報告和資料擷取的到期窗口限制仍為九個月；報告和資料擷取的傳遞將在此期間結束時暫停，除非重新啟用排程。<p>再次強調，這些功能將在 2023 年 1 月 31 日淘汰。在此日期之前，您必須將排程報告遷移至 Adobe Analytics 中任何您可以使用的其他機制之一。如有其他問題或需要支援，請和 Adobe 客戶服務聯絡。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **暫停 Report Builder 中的排程工作** | 2022 年 6 月 8 日 | 在 2022 年 4 月 21 日，我們對 Report Builder 中的排程工作推出變更，這屬於我們效能和傳遞最佳化工作的一部分。這些變更包括移除已排程傳遞在「x 次發生次數後結束」的能力。因應多位客戶要求更多時間以便探索和實施替代方案，我們決定以有限的方式恢復此選項，直到 **2023 年 1 月 31 日**。<p>您可繼續排程每小時 Report Builder 工作，並在最多 99 次發生次數後結束。請注意，回復僅適用於每小時工作；「x 次發生次數後結束」仍不適用於所有其他傳遞間隔 (每日、每週、每月和每年)。請注意，此選項將於 2023 年 1 月 31 日停止使用。如有更多問題或需要支援，請聯絡 Adobe 客戶服務。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP 升級** | 2022 年 5 月 9 日 | 此前，我們曾告知 Adobe 將在 2022 年 5 月升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。我們已將此升級推遲到 **2022 年夏天**。進行此變更後，將不再支援某些 SFTP 用戶端設定。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)詳述的變更。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;&quot;

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


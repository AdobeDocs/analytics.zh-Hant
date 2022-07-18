---
title: 最新 Analytics 版本注意事項
description: 檢視目前的 Adobe Analytics 版本注意事項。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: bedda6ba1f3022562976ada7e73a9514947b5071
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 55%

---

# 本Adobe Analytics發行說明（2022年7月）

**上次更新**:2022年7月13日

>[!NOTE]
>
>此頁面包含搶鮮版資訊並可能視情況變動。

## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 版本注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

## Adobe Analytics 新功能

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| XDM中邊緣收集商品變數的支援 | 使客戶能夠通過體驗邊緣/Web SDK收集資料，以使用XDM為促銷變數(eVar)指定各種值。 [了解更多](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar-merchandising.html?lang=en) | 2022 年 6 月 29 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修復某些段轉換錯誤。 (AN-291262、AN-294092)

**為個別客戶進行的修正**:

AN-280192;AN-281628;AN-287022;AN-287104;AN-287876;AN-288802;AN-288457;AN-288779;AN-288799;AN-289198;AN-289852;AN-289931;AN-290162;AN-290213;AN-291059;AN-291090;AN-291270;AN-294091;AN-294135;AN-294152;AN-294158;AN-294285;AN-294317;AN-294404;AN-294531;AN-294769;AN-294984;AN-295172;AN-295211;AN-295224;AN-295413;AN-295440;AN-295465;AN-295499;AN-295516;

## 給 Adobe Analytics 管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **系統生成的電子郵件的新域** | 2022 年 7 月 13 日 | 開 **2022年5月18日**,Adobe更改了發件人的域，以獲取來自Workspace項目、警報和超時警報的電子郵件， `noreply@omniture.com` 至 `noreply@adobe.com`。 如果您的組織僅允許特定發件人，請將此新電子郵件添加到允許清單。 |
| **更新到新的NetAcuity電信公司資料庫** | 2022 年 7 月 11 日 | **2022年10月起**，儲存在 `carrier` Adobe AnalyticsData Warehouse和分析資料源中的欄位將發生變化。 以往，該列中的資料格式 `<domain>:<ISP>`。 Adobe維護了內部查找表以映射這些 `<domain>:<ISP>` 將值轉換為運營商名稱以在Adobe Analytics報告工具(Analysis Workspace、報告和分析、報告API、資料倉庫、LiveStream等)中進行報告 查找檔案(carrier.tsv)還提供有資料饋送，以便資料饋送客戶可以使用相同的映射。<p>此更新通過使用NetAcuity中更準確的載波資料庫增強了我們的載波映射。 資料饋送中載波列中資料的格式將隨後更改。 而不是 `<domain>:<ISP>`，它將包含承運人名稱。 Adobe將繼續使用查找表，以盡可能保持與過去報告的連續性。 Adobe應用查找的報告工具(Analysis Workspace、報告和分析、報告API、資料倉庫、LiveStream等) 將從更精確的映射中獲益。 某些映射 — 特別是對於國際域和ISP — 在我們採用新資料庫時將比其他映射更改。 資料饋送載波查找檔案(carrier.tsv)將維護舊映射並添加新映射。<p>分析源連接器當前未映射承運人欄位，因此承運人報告當前在AEP、CJA等中不可用。 因此，使用新的運營商資料庫不會影響基於分析源連接器提供的資料的AEP中的任何內容。 |
| **改進的IP到地理位置映射** | 2022 年 7 月 11 日 | 我們的IP查找供應商Digital Element正在升級到新的改進資料集(NetAcuity Pulse)，用於IP到地理位置映射。 Adobe Analytics將在 **2022年10月** 時間範圍。 新資料庫將比以前的版本更準確。 當採用新資料庫時，某些IP到地理的映射會發生變化/改進。<p>所有Adobe Analytics工具(Analysis Workspace、報告和分析、報告API、資料倉庫、LiveStream、資料源等) 將自動利用新的改進映射。 資料饋送中的資料格式不會更改。 通過分析源連接器提供的CJA資料也將自動利用新映射。 |
| **暫停 Reports &amp; Analytics 中的排程報告** | 2022 年 6 月 8 日 | 在 2022 年 4 月 21 日，我們宣布淘汰排程報告的幾個特定功能，為先前宣布的 Reports &amp; Analytics 生命週期結束做準備。這些功能包括排程新報告，以及擷取新資料的能力。<p>因應客戶要求延長以及為了順利從 Reports and Analytics 進行轉換，我們決定將這些功能的存取權延長到 **2023 年 1 月 31 日**。請注意，報告和資料擷取的到期窗口限制仍為九個月；報告和資料擷取的傳遞將在此期間結束時暫停，除非重新啟用排程。<p>再次強調，這些功能將在 2023 年 1 月 31 日淘汰。在此日期之前，您必須將排程報告遷移至 Adobe Analytics 中任何您可以使用的其他機制之一。如有其他問題或需要支援，請和 Adobe 客戶服務聯絡。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **暫停 Report Builder 中的排程工作** | 2022 年 6 月 8 日 | 在 2022 年 4 月 21 日，我們對 Report Builder 中的排程工作推出變更，這屬於我們效能和傳遞最佳化工作的一部分。這些變更包括移除已排程傳遞在「x 次發生次數後結束」的能力。因應多位客戶要求更多時間以便探索和實施替代方案，我們決定以有限的方式恢復此選項，直到 **2023 年 1 月 31 日**。<p>您可繼續排程每小時 Report Builder 工作，並在最多 99 次發生次數後結束。請注意，回復僅適用於每小時工作；「x 次發生次數後結束」仍不適用於所有其他傳遞間隔 (每日、每週、每月和每年)。請注意，此選項將於 2023 年 1 月 31 日停止使用。如有更多問題或需要支援，請聯絡 Adobe 客戶服務。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP 升級** | 2022 年 5 月 9 日 | 此前，我們曾告知 Adobe 將在 2022 年 5 月升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。我們已將此升級推遲到 **2022 年夏天**。進行此變更後，將不再支援某些 SFTP 用戶端設定。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hant)詳述的變更。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;&quot;

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


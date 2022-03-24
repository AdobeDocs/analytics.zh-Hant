---
title: 最新 Analytics 版本注意事項
description: 檢視目前的 Adobe Analytics 版本注意事項。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 0eb88df05909be28877ac266655f7959cc086044
workflow-type: tm+mt
source-wordcount: '1001'
ht-degree: 78%

---

# Adobe Analytics 目前的版本注意事項 (2022 年 3 月)

**上次更新日期: 2022 年 3 月 23 日**

* 如需 2022 年 2 月版本注意事項，請至[這裡](/help/release-notes/2022.md)。
* 了解關於 [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。取得 Experience League 上的最新自助文件、教學課程和課程。

## Adobe Analytics 新功能 {#aa-features}

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| 工作區中的註解 | 工作區中的註解讓您能夠有效地將內容相關的資料細微差別和深入解析傳達給您的組織。[了解更多](/help/analyze/analysis-workspace/components/annotations/overview.md) | 逐步推出於2022年3月23日。 一般可用性：2022年4月11日 |
| Adobe Analytics 登陸頁面更新 | 對聯合Workspace/Reports &amp; Analytics登錄頁的更新，可提高可用性和導航方便性。 [了解更多](/help/analyze/landing.md) | 2022年4月1日 |
| [!UICONTROL 下一項] 或 [!UICONTROL 上一項] 工作區面板 | 的 [!UICONTROL 下一項或上一項] 「面板」(Panel)允許您瀏覽所選維項後面或前面的項。 例如，如果希望查看特定產品頁面、市場營銷渠道甚至設備類型的下一頁或上一頁，請使用它。 此面板超越了舊版本的下一次/上一次報告，因為它允許您查看任何維，並且不需要任何新的實施來獲得洞察力。 | 2022年4月1日 |
| [!UICONTROL 頁面摘要] 工作區面板 | 的 [!UICONTROL 頁面摘要] 面板為您選擇的頁面提供深度分析。 它提供與舊式報告和分析相同的詳細資訊 [!UICONTROL 頁面摘要] 報告，再加上更多。 | 2022年4月1日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修正嘗試存取 Activity Map 時造成錯誤的問題。(AN-267177)
* 已修正不成功的使用者資產轉移的問題。(AN-279813)
* 已修正 A4T 工作區面板的問題。(AN-281594；AN-282418)
* 已修正部分使用者無法存取 Adobe Analytics 的問題。 (AN-282776)
* 已修正部分新建報表套裝無法收集資料的問題。(AN-283114、AN-283311)
* 已修正無法使用作業系統維度刪除 Win11 的問題。(AN-275569、AN-275727；AN-280335)
* 已修正錯誤傳送資料摘要電子郵件的問題。 (AN-280255；AN-282051)


### Adobe Analytics 中的其他修正

AN-256929;AN-270937;AN-272158;AN-275130;AN-277830;AN-278635;AN-279066;AN-279683;AN-279899;AN-280504;AN-280617;AN-280663;AN-281423;AN-281523;AN-281608;AN-281671;AN-281963;AN-282027;AN-282218;AN-282593;AN-282605;AN-282632;AN-282654;AN-282694;AN-282744;AN-282756;AN-282804;AN-282838;AN-282862;AN-282903;AN-282937;AN-282892;AN-283315;AN-283338;AN-283388;AN-283417;AN-283474;AN-283511;AN-283691、AN-283895;AN-283943;AN-283957;AN-284030;AN-284100;AN-284142;AN-284162

## 給 Adobe Analytics 管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 暫停較舊的排程報告 | 2022 年 3 月 11 日 | 自 **2022 年 4 月 15 日**&#x200B;起，Adobe 打算暫停所有建立日期超過兩年的排程報告 (在 2020 年 1 月 31 日之前建立的)。不會刪除任何報表或資料。只有被確認為超過兩年的報表才會被暫停，並且不會發送額外的排程報告。[了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 ISO 區域更新 | 2021 年 3 月 11 日 | Adobe 將於 **2022 年 6 月 10 日**&#x200B;執行 2022 ISO 區域更新。 預計此版本後將會有較小的更新。 |
| 更改 Analytics 處理透過 Experience Edge 收集的 A4T 資料的方式 | 2022 年 2 月 25 日 | 開 **2022年3月7日**，我們更改了處理通過Experience Edge發送到Adobe Analytics的某些與目標相關的資料的方式。 在使用包含 Analytics 和 Target 的 Adobe Experience Platform Web SDK 時，部分個人化事件在 [!DNL Adobe Analytics] 中會計入[!UICONTROL 頁面檢視量]。 這會導致頁面檢視計數擴增以及額外的伺服器呼叫。更改後，將忽略沒有分析內容的個性化呼叫。 使用 A4T 資料的個人化呼叫將記錄 A4T 資料，但不會記錄為計費的伺服器呼叫，也不會影響頁面檢視量或連結事件量度。 |
| 暫停較舊的已排程 Report Builder 工作 | 2022 年 2 月 24 日 | **自 2022 年 4 月 15 日起**，Adobe 打算暫停所有建立日期超過兩年的已排程 Report Builder 工作。這項暫停尤其會套用在 2020 年 1 月 31 日之前建立的任何工作上。 不會刪除任何工作、活頁簿或資料。但是將暫停確認超過兩年的工作，並且不會發送額外的排程工作。[了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| 舊版 Analytics OAuth/JWT 整合的允許清單 EOL 延長到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和舊版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允許清單延長即將到期。此延長是為了讓使用舊版 [!DNL Adobe Analytics] OAuth/JWT 認證的客戶有更多時間，以便將其用戶端整合移轉至 [Adobe IMS 認證](https://developer.adobe.com/console)。這項到期會影響 (但不限於) 尚未完成所需 IMS 移轉的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客戶。 目前透過允許清單擴展功能使用舊版 [!DNL Analytics] OAuth/JWT 憑證的客戶，以及在 2022 年 5 月 25 日尚未完成移轉至 IMS 的客戶，都將會失去使用 Adobe 服務的權限。直播串流客戶可參考這些將其客戶應用程式移轉至 IMS 憑證的[說明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。 [!DNL Campaign] 客戶可與他們的 Adobe 帳戶團隊聯絡，了解關於升級至最新版本 [!DNL Campaign] 的詳情。 |
| 安全檔案傳輸通訊協定 (SFTP) 服務升級 | 2022 年 3 月 3 日 | 在 **2022 年 5 月 15 日**，[!DNL Adobe Analytics] 將會升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。在這次變更後，我們將不再支援某些 SFTP 用戶端設定。我們也會新增一些連線選項，這些選項將會在 **2022 年 3 月 1 日**&#x200B;之前提供。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hant)詳述的變更。 |
| [!DNL Reports & Analytics] EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

## AppMeasurement {#appm}

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 版本注意事項](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 版本注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)

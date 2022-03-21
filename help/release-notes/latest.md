---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 99572e3ed2b519b5479a31680a48c17e2aed4fd9
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 52%

---

# 本Adobe Analytics發行說明（2022年3月）

**上次更新日期: 2022 年 3 月 21 日**

>[!IMPORTANT]
>
>以下內容包含預發行資訊，並且可能會更改。

* 有關2022年2月發行說明，請轉到 [這裡](/help/release-notes/2022.md)。
* 了解關於 [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。取得 Experience League 上的最新自助文件、教學課程和課程。

## Adobe Analytics 新功能 {#aa-features}

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| 工作區中的注釋 | Workspace中的注釋使您能夠有效地將上下文資料細微差別和洞察力傳達給您的組織。 [了解更多](/help/analyze/analysis-workspace/components/annotations/overview.md) | 2022年3月23日 |
| Adobe Analytics登錄頁更新 | 對聯合Workspace/Reports &amp; Analytics登錄頁的更新，可提高可用性並簡化導航。 [了解更多](/help/analyze/landing.md) | 2022年4月1日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修復在嘗試訪問Activity Map時導致錯誤的問題。 (AN-267177)
* 修復了用戶資產轉移失敗的問題。 (AN-279813)
* 已修復A4T工作區面板的問題。 (AN-281594；AN-282418)
* 解決了某些用戶無法訪問Adobe Analytics的問題。 (AN-282776)
* 修復了某些新建立的報告套件未收集資料的問題。 (AN-283114、AN-283311)
* 已修復無法使用作業系統維度檢測Win11的問題。 (AN-275569、AN-275727;AN-280335)
* 修復了錯誤發送的資料源電子郵件的問題。 (AN-280255；AN-282051)


### Adobe Analytics 中的其他修正

AN-256929;AN-270937;AN-272158;AN-275130;AN-277830;AN-278635;AN-279066;AN-279683;AN-279899;AN-280504;AN-280617;AN-280663;AN-281423;AN-281523;AN-281608;AN-281671;AN-281963;AN-282027;AN-282218;AN-282593;AN-282605;AN-282632;AN-282654;AN-282694;AN-282744;AN-282756;AN-282804;AN-282838;AN-282862;AN-282903;AN-282937;AN-282892;AN-283315;AN-283338;AN-283388;AN-283417;AN-283474;AN-283511;AN-283691、AN-283895;AN-283943;AN-283957;AN-284030;AN-284100;AN-284142;AN-284162

## Adobe Analytics管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 暫停較舊的計畫報告 | 2022年3月11日 | 有效 **2022年4月15日**,Adobe打算暫停建立日期超過兩年（在2020年1月31日之前建立）的所有計畫報告。 不會刪除任何報告或資料。 將只暫停標識為兩年以上的報告，並且不會發送其他計畫的報告。 [了解更多](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 ISO 地區更新 | 2021 年 3 月 11 日 | Adobe將在 **2022年6月10日**。 預計此版本後將會有較小的更新。 |
| 更改分析處理通過體驗邊緣收集的A4T資料的方式 | 2022 年 2 月 25 日 | 開 **2022年3月7日**，我們更改了處理通過Experience Edge發送到Adobe Analytics的某些與目標相關的資料的方式。 將Adobe Experience PlatformWeb SDK與分析和目標一起使用時，某些個性化事件被計入 [!DNL Adobe Analytics] 如 [!UICONTROL 頁面視圖]。 這導致頁面視圖數量膨脹，並導致額外的伺服器調用。 更改後，將忽略沒有分析內容的個性化呼叫。 使用A4T資料的個性化調用將記錄A4T資料，但不會記錄為可計費伺服器調用，也不會影響頁面視圖或連結事件度量。 |
| 暫停較舊的計畫Report Builder任務 | 2022 年 2 月 24 日 | **自2022年4月15日起生效**,Adobe打算暫停兩年多前建立的所有計畫Report Builder任務。 具體而言，暫停適用於2020年1月31日之前建立的任何任務。 不會刪除任務、工作簿或資料。 但是，將暫停被標識為兩年以上的任務，並且不會發送其他計畫任務。 [了解更多](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| 舊版 Analytics OAuth/JWT 整合的允許清單 EOL 延長到期 | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和舊版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允許清單延長即將到期。此延長是為了讓使用舊版 [!DNL Adobe Analytics] OAuth/JWT 認證的客戶有更多時間，以便將其用戶端整合移轉至 [Adobe IMS 認證](https://developer.adobe.com/console)。這項到期會影響 (但不限於) 尚未完成所需 IMS 移轉的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客戶。 目前透過允許清單擴展功能使用舊版 [!DNL Analytics] OAuth/JWT 憑證的客戶，以及在 2022 年 5 月 25 日尚未完成移轉至 IMS 的客戶，都將會失去使用 Adobe 服務的權限。直播串流客戶可參考這些將其客戶應用程式移轉至 IMS 憑證的[說明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。 [!DNL Campaign] 客戶可與他們的 Adobe 帳戶團隊聯絡，了解關於升級至最新版本 [!DNL Campaign] 的詳情。 |
| 安全檔案傳輸通訊協定 (SFTP) 服務升級 | 2022 年 3 月 3 日 | 在 **2022 年 5 月 15 日**，[!DNL Adobe Analytics] 將會升級其安全檔案傳輸通訊協定 (SFTP) 服務，以提供改良的檔案傳輸安全性功能。在這次變更後，我們將不再支援某些 SFTP 用戶端設定。我們也會新增一些連線選項，這些選項將會在 **2022 年 3 月 1 日**&#x200B;之前提供。這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html)詳述的變更。 |
| [!DNL Reports & Analytics] EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

## AppMeasurement {#appm}

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-TW)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-TW)

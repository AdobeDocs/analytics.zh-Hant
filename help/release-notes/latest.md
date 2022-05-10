---
title: 最新 Analytics 版本注意事項
description: 檢視目前的 Adobe Analytics 版本注意事項。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 43869c683ca30c94157c6822b53f02a917f6e3ff
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 95%

---

# Adobe Analytics 目前的版本注意事項 (2022 年 4 月)

**上次更新**:2022年5月9日

## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 版本注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [媒體分析發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

## Adobe Analytics 新功能

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| Adobe Analytics 登陸頁面更新 | 更新工作區/Reports &amp; Analytics 聯合登陸頁面，可改善可用性並方便瀏覽。[了解更多](/help/analyze/landing.md) | 2022 年 4 月 20 日 |
| 「[!UICONTROL 下一個項目]」或「[!UICONTROL 上一個項目]」工作區面板 | [!UICONTROL 「下一個項目」或「上一個項目」]面板可讓您瀏覽您所選維度項目之後或之前的項目。例如，如果您想查看特定產品頁面、行銷頻道甚至裝置類型的下一頁或上一頁，請使用它。此面板超越傳統的下一個/上一個報告，因為它可讓您查看任何維度，並且不需要任何新的實施即可獲得見解。[了解更多](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 2022 年 4 月 20 日 |
| 「[!UICONTROL 頁面摘要]」工作區面板 | 「[!UICONTROL 頁面摘要]」面板為您選擇的頁面提供深入分析。它提供與舊版 Reports &amp; Analytics「[!UICONTROL 頁面摘要]」報告相同的詳細資料，還有其他更多資訊。[了解更多](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 2022 年 4 月 20 日 |
| 2.0 API 呼叫 `x-proxy-global-company-id` 標題規定已移除 | Adobe Analytics 2.0 API 不再規定要 `x-proxy-global-company-id` 標題，因為此資訊是端點 URL 的一部分。您仍然可以包含此標題，但是若沒有標題也不會再發生錯誤。 | 2022 年 4 月 20 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修正資料摘要中的問題：在建立資料摘要 UI 且儲存資料摘要後，開始和結束日期會自動變更。日期在 1 天內會自我更新。(AN-281262)
* 已修正透過電子郵件連結續訂預定專案受阻的問題。(AN-283622)
* 已修復促成 Apple Safari 和 Microsoft Edge 發佈最新版本的一個問題；這個問題在 Adobe 瀏覽器類型查詢表中未被正確識別。類似[瀏覽器更新](/help/components/dimensions/browser.md)的情況，瀏覽器類型的查詢表更新只會更正以後的資料。瀏覽器版本的查詢表已於 4 月 20 日更新，瀏覽器類型的查詢表已於 4 月 28 日更新。(AN-284872；AN-285753；AN-286257)

### Adobe Analytics 中的其他修正

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761

## 給 Adobe Analytics 管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **SFTP升級** | 2022 年 5 月 9 日 | 以前，我們曾通知Adobe將在2022年5月升級其安全檔案傳輸協定(SFTP)服務，以提高檔案傳輸的安全性。 我們已將升級日期推遲至2022年夏天。 發生此更改時，將不再支援某些SFTP客戶端配置。 這只會影響使用 SFTP 傳送給 Adobe Analytics 或從中擷取的資料。FTP 通訊協定不受影響。為避免服務中斷，請確保您的 SFTP 用戶端 (程式碼、工具、服務) 符合[此處](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=zh-Hant)詳述的變更。 |
| **跨裝置分析 (CDA) 權益** | 2022 年 4 月 13 日 | 自 **2022 年 5 月 1 日開始**，任何新實施的 [CDA](/help/components/cda/overview.md) 會限制為每位客戶最多三個報告套件 ID (RSID)。 |
| **變更 Adobe Analytics 處理透過 Experience Edge 所收集 A4T 資料的方式** | 2022 年 3 月 31 日 | 在 2022 年 3 月 7 日，Analytics 已變更處理 Experience Edge 所傳部分呼叫的方式，其中包含針對 Target (A4T) 報告的 Analytics Target 內容。自 3 月 7 日起，含 A4T 報告內容的所有點擊都經過修改，所以不會被視為頁面檢視或連結事件。自 **2022 年 3 月 31 日**&#x200B;起，邏輯更具選擇性，這樣系統就不會修改標準的頁面檢視和「點擊」事件。以後，唯一修改的事件為只含 A4T 內容的個人化呼叫。 |
| **更新支援部分客戶的瀏覽器加密方法** | 2022 年 3 月 28 日 | Adobe 提供兩種密碼安全級別，以滿足不同客戶對第一方數據收集的安全需求。**2022 年 6 月 23 日** 起，對於安全等級設定為「高」的客戶，部分 HTTPS 加密算法 (稱為加密) 的支援服務會被移除。此操作表示有些較舊版作業系統無法再將數據發送到 Analytics，因為這些系統不支援現代化的加密方法。使用預設「標準」密碼安全設定的客戶不會受到影響。我們已聯絡過目前設定為「高」等級的所有客戶。受此變動影響的加密詳細列表可在此處查看。 |
| **暫停較舊的排程報告** | 2022 年 4 月 12 日 | 自 **2022 年 4 月 20 日**&#x200B;起，Adobe 打算暫停所有建立日期超過兩年的排程報告 (在 2020 年 1 月 31 日之前建立的)。不會刪除任何報表或資料。只有被確認為超過兩年的報表才會被暫停，並且不會發送額外的排程報告。了解更多 |
| **2022 ISO 區域更新** | 2021 年 3 月 11 日 | Adobe 預計在 **2022 年 6 月 10 日**&#x200B;執行 2022 ISO 區域更新。 預計此版本後將會有較小的地區資訊更新。 |
| **暫停較舊的已排程 Report Builder 工作** | 2022 年 4 月 12 日 | 自 **2022 年 4 月 20 日**&#x200B;起，Adobe 打算暫停所有建立日期超過兩年的已排程 Report Builder 工作。這項暫停尤其會套用在 2020 年 1 月 31 日之前建立的任何工作上。 不會刪除任何工作、活頁簿或資料。但是會暫停確認超過兩年的工作，並且不會發送額外的排程工作。了解更多 |
| **舊版 Analytics OAuth/JWT 整合的允許清單 EOL 延長到期** | 2022 年 1 月 14 日 | 在 **2022 年 5 月 25 日**，[Analytics 1.3 API、1.4 SOAP API 和舊版 Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 允許清單延長已到期。此延長是為了讓使用舊版 [!DNL Adobe Analytics] OAuth/JWT 認證的客戶有更多時間，以便將其用戶端整合移轉至 [Adobe IMS 認證](https://developer.adobe.com/console)。這項到期會影響 (但不限於) 尚未完成所需 IMS 移轉的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客戶。 目前透過允許清單擴展功能使用舊版 [!DNL Analytics] OAuth/JWT 憑證的客戶，以及在 2022 年 5 月 25 日尚未完成移轉至 IMS 的客戶，都會失去使用 Adobe 服務的權限。直播串流客戶可參考這些將其客戶應用程式移轉至 IMS 憑證的[說明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。 [!DNL Campaign] 客戶可與他們的 Adobe 帳戶團隊聯絡，了解關於升級至最新版本 [!DNL Campaign] 的詳情。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;&quot;

## AppMeasurement {#appm}

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 版本注意事項](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 版本注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)

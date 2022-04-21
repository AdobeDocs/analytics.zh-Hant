---
title: 最新 Analytics 版本注意事項
description: 檢視目前的 Adobe Analytics 版本注意事項。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b93b27fac0a9e3364512bb8a27ad64c7eb379dd1
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 68%

---

# Adobe Analytics 目前的版本注意事項 (2022 年 4 月)

**上次更新日期**：2022 年 4 月 19 日

* 如需 2022 年 3 月版本注意事項，請前往[這裡](/help/release-notes/2022.md)。

* 如需 Customer Journey Analytics 版本注意事項，請前往[此處](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)。

* 如需 Media Analytics 版本注意事項，請前往[此處](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)。

* 了解關於 [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。取得 Experience League 上的最新自助文件、教學課程和課程。

| 功能 | 說明 | [目標日期](releases.md) |
| ----------- | ---------- | ------- |
| Adobe Analytics 登陸頁面更新 | 更新工作區/Reports &amp; Analytics 聯合登陸頁面，可改善可用性並方便瀏覽。[了解更多](/help/analyze/landing.md) | 2022 年 4 月 20 日 |
| 「[!UICONTROL 下一個項目]」或「[!UICONTROL 上一個項目]」工作區面板 | [!UICONTROL 「下一個項目」或「上一個項目」]面板可讓您瀏覽您所選維度項目之後或之前的項目。例如，如果您想查看特定產品頁面、行銷頻道甚至裝置類型的下一頁或上一頁，請使用它。此面板超越傳統的下一個/上一個報告，因為它可讓您查看任何維度，並且不需要任何新的實施即可獲得見解。[了解更多](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 2022 年 4 月 20 日 |
| 「[!UICONTROL 頁面摘要]」工作區面板 | 「[!UICONTROL 頁面摘要]」面板為您選擇的頁面提供深入分析。它提供與舊版 Reports &amp; Analytics「[!UICONTROL 頁面摘要]」報告相同的詳細資料，還有其他更多資訊。[了解更多](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 2022 年 4 月 20 日 |
| 已刪除 `x-proxy-global-company-id` 2.0 API調用的標頭 | Adobe Analytics2.0 API不再要求 `x-proxy-global-company-id` 標題，因為此資訊是終結點URL的一部分。 您仍可以包括此標頭，但如果缺少該標頭，則不再引發錯誤。 | 2022 年 4 月 20 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics 中的修正

* 已修正資料摘要中的問題：在建立資料摘要 UI 且儲存資料摘要後，開始和結束日期會自動變更。日期在 1 天內會自我更新。(AN-281262)

* 已修正透過電子郵件連結續訂預定專案受阻的問題。(AN-283622)

### Adobe Analytics 中的其他修正

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761;

## 給 Adobe Analytics 管理員的重要通知

| 注意 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **跨裝置分析 (CDA) 權益** | 2022 年 4 月 13 日 | 有效 **2022年5月1日**，任何新的實施 [CDA](/help/components/cda/overview.md) 限制為每個客戶最多三個報告套件ID(RSID)。 |
| **變更 Adobe Analytics 處理透過 Experience Edge 所收集 A4T 資料的方式** | 2022 年 3 月 31 日 | 2022年3月7日，Analytics更改了它處理來自體驗邊緣的一些呼叫的方式，這些呼叫包括用於目標(A4T)分析報告的目標內容。 從3月7日起，所有A4T報告內容的點擊都將被修改，因此它們不會被視為頁面視圖或連結事件。 開始 **2022年3月31日**，邏輯更具選擇性，因此不會修改標準頁面視圖和按一下事件。 今後，僅修改的事件是僅包含A4T內容的個性化調用。 |
| **更新支援部分客戶的瀏覽器加密方法** | 2022 年 3 月 28 日 | Adobe 提供兩種密碼安全級別，以滿足不同客戶對第一方數據收集的安全需求。開 **2022年6月23日** 對某些HTTPS加密算法（稱為密碼）的支援被刪除，這些加密算法的安全級別設定為「高」。 此操作意味著某些較舊的作業系統不再能夠將資料發送到分析，因為它們不支援現代加密方法。 使用預設「標準」密碼安全設定的客戶不受影響。 我們已聯絡過目前設定為「高」等級的所有客戶。此處可找到受此更改影響的密碼的詳細清單。 |
| **暫停較舊的排程報告** | 2022 年 4 月 12 日 | 自 **2022 年 4 月 20 日**&#x200B;起，Adobe 打算暫停所有建立日期超過兩年的排程報告 (在 2020 年 1 月 31 日之前建立的)。未刪除任何報告或資料。 只暫停標識為兩年以上的報告，並且不發送其他計畫的報告。 了解更多 |
| **2022 ISO 區域更新** | 2021 年 3 月 11 日 | Adobe計畫執行2022 ISO區域更新 **2022年6月10日**。 預計此版本後將會有較小的地區資訊更新。 |
| **暫停較舊的已排程 Report Builder 工作** | 2022 年 4 月 12 日 | 自 **2022 年 4 月 20 日**&#x200B;起，Adobe 打算暫停所有建立日期超過兩年的已排程 Report Builder 工作。這項暫停尤其會套用在 2020 年 1 月 31 日之前建立的任何工作上。 未刪除任務、工作簿或資料。 但是，被標識為兩年以上的任務被暫停，並且不會發送其他計畫任務。 了解更多 |
| **舊版 Analytics OAuth/JWT 整合的允許清單 EOL 延長到期** | 2022 年 1 月 14 日 | 開 **2022年5月25日**，也請參見Wiki頁。 [分析1.3 API、1.4 SOAP API和Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) allowlist擴展過期。 此延長是為了讓使用舊版 [!DNL Adobe Analytics] OAuth/JWT 認證的客戶有更多時間，以便將其用戶端整合移轉至 [Adobe IMS 認證](https://developer.adobe.com/console)。這項到期會影響 (但不限於) 尚未完成所需 IMS 移轉的 [!DNL Adobe Analytics Livestream] 和 [!DNL Adobe Campaign] 客戶。 當前使用舊式服務的客戶 [!DNL Analytics] 通過允許清單擴展的OAuth/JWT憑據，以及在2022年5月25日之前未完成向IMS憑據遷移的憑據的用戶無法訪問Adobe服務。 直播串流客戶可參考這些將其客戶應用程式移轉至 IMS 憑證的[說明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md)。 [!DNL Campaign] 客戶可與他們的 Adobe 帳戶團隊聯絡，了解關於升級至最新版本 [!DNL Campaign] 的詳情。 |
| **[!DNL Reports & Analytics]** EOL | 2022 年 1 月 4 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術等功能，不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束程序。 |

{style=&quot;table-layout:auto&quot;&quot;

## AppMeasurement {#appm}

如需 AppMeasurement 版本 (版本 2.22.4) 最新的更新，請參閱 [AppMeasurement for JavaScript 版本注意事項](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] 版本注意事項](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)

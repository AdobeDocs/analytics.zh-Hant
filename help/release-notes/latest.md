---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 97a63c42a121204e043d308525518d16e44b21f9
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 50%

---

# Adobe Analytics 目前的版本注意事項 (2024 年 5 月)

**上次更新**：2024年5月15日

這些發行說明涵蓋2024年5月15日到6月的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **有關從Adobe Analytics升級至Customer Journey Analytics的新檔案** | 對於從Adobe Analytics升級至Customer Journey Analytics的組織，根據組織目前的Adobe Analytics實作和長期目標，有多種升級選項和許多需要牢記的考量事項。 現在提供新的文件資源來協助您更加瞭解：<ul><li>存在的各種升級路徑</li><li>根據組織目前的 Adobe Analytics 實作可以使用哪些升級路徑</li><li>每種升級路徑的優點和缺點</li><li>每個升級路徑的逐步操作指導</li><li>處理歷史資料的考量事項</li></ul>[開始升級至Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 現在可用 |
| **設定 `contextData` 欄位透過XDM** | 透過體驗Edge Network傳送資料至Adobe Analytics的客戶可以 [設定內容資料值](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/contextdata) 直接在XDM中或裝載的「資料」部分中。 |  | 現在可用 |
| **Analytics即時報表2.0 API** | Adobe Analytics中的新即時報告API 2.0改善了客戶整合併提供快速的報告結果。 這些結果可以以程式設計方式用於基本、趨勢和劃分報表。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 2024年5月30日 |
| **串流媒體：使用Web SDK傳送Web資料至Adobe Experience Platform Edge Network** | 您現在可以使用Adobe Experience Platform Web SDK將串流媒體網頁資料傳送到Adobe Experience Platform Edge Network。 此增強功能可讓您建立更個人化的行銷活動，並提供更個人化的內容，產生更多可報告的追蹤資料。<p>這項變更針對所有平台解決方案(例如Customer Journey Analytics、Adobe即時CDP、Adobe Journey Optimizer和事件轉送)的Web實作提供統一的收集方法。 過去，將串流媒體網頁資料傳送至Edge Network的唯一方式是使用Media Edge API。 [瞭解更多即將關注的內容] | | 2024 年 5 月 31 日 |
| **提高預設低流臨界值** | 在 **2024 年 4 月中旬**，Adobe 將開始提高預設報告套裝低流量臨界值，如下所示： ![低流量臨界值](assets/thresholds.png) 這只會影響目前設定低於新臨界值的變數。這些改變將逐步進行，我們預計這項工作將在&#x200B;**五月底**&#x200B;結束。隨著這些增加的推出，您可能會注意到高基數變數的變化：<ul><li>更多維度值可用於報告。</li><li>區段和計算量度可能包含更多資料。</li><li>以區段為主的虛擬報告套裝可能包含更多資料。</li><li>分類匯出可能包含更多資料。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月 31 日 |
| **Activity Map減少Web SDK的伺服器呼叫** | 目前，Activity Map 連結事件被視為是其本身事件並會產生額外費用。此增強功能會擷取一些連結事件，並將它們封裝到下一次點選中，類似於AppMeasurement處理事件的方式。 (後續文件) | Beta版於2024年5月31日開始 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正下列分類問題：AN-343186、AN-344711、AN-344856、AN-345094、AN-345179、AN-346265、AN-345288、AN-346339、AN-346560、AN-347572、AN-347681、AN-347768、AN-348024
* 修正下列Data Warehouse問題：AN-346789、AN-347031、AN-347568；
* 已修正下列資料摘要問題： AN-343616、AN-345831、AN-345988、AN-346124、AN-346232、AN-346972、AN-347680、AN-347755、AN-347954
* 修正下列資料來源問題： AN-347890；
* 修正下列Analysis Workspace問題：AN-321503、AN-343103、AN-343471、AN-345171、AN-345223、AN-345912、AN-346026、AN-346330、AN-346839、AN-347679
* 已修正下列A4T問題： AN-345118；

### Analytics 其他修正

AN-327749、AN-332949、AN-342881、AN-343171、AN-343708、AN-344034、AN-345559、AN-346023、AN-346230、AN-346330、AN-346469、AN-346606、AN-346750、AN-346973、AN-347026、AN-347110、AN-347439；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **ISO區域更新** | 2024年5月10日 | Adobe將於2024年6月7日執行2024 ISO區域更新。 預計此版本後將會有較小的地區資訊更新。 |
| **13 個月的儲存有效期`cust_visids`** | 2024 年 3 月 20 日 | 即將發行的 Analytics Hit 處理引擎 (預計於 4 月或 5 月發行) 將開始強制執行 13 個月的 `cust_visids` 儲存有效期。如果報告套裝已啟用「啟用訪客聯繫」，則此設定用於尋找 `cust_visid` 是否有點擊時無 `cust_visid` 的 `visid_high/visid_low value`。目前，`visid_high/visid_low` 的 `cust_visid` 對應不會過期。在此版本中，如果自以下時間以來已過13個月或更久 `visid_high/visid_low` 曾經 `cust_visid` 在點選上，對應會過期。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2023 年舊版發行說明](/help/release-notes/2023.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7dd42948073b56a33c1d00f9b4292d1cc3416470
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 65%

---

# 最新 Adobe Analytics 版本注意事項 (2024 年 9 月)


**上次更新日期**：2024年9月11日

這些發行說明涵蓋2024年9月11日到10月初的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
|--- | --- | --- | --- |
| **計算量度管理器和區段管理器的「使用於」欄中的額外資訊** | 計算量度管理器和區段管理器的「使用於」欄包含以下新報告區域：<ul><li>**Report Builder**：顯示Report Builder中使用的計算量度或區段數。</li><li>**臨時元件**：顯示專案中使用的臨時計算量度或臨時區段數目。 這些臨時計算量度和區段 (也稱為「快速計算量度」和「快速區段」) 只能在建立這些量度和區段的專案中使用，因此在「使用於」欄中，這些量度和區段會與「專案」報告區域分開報告。</li></ul>如需詳細資訊，請參閱[計算量度管理員](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager)和[區段管理員](https://experienceleague.adobe.com/en/docs/analytics/components/segmentation/segmentation-workflow/seg-manage)。 |  | 2024年9月11日 |
| **Activity Mapv3延伸模組** | Activity Map v3擴充功能現已推出。 如果您已安裝v2擴充功能，請先解除安裝再安裝v3擴充功能。 導覽至&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Activity Map]**，以取得最新版本的擴充功能。 |  | 2024年9月3日 |


## Adobe Analytics 中的修正

A4T： AN-355736
Activity Map： AN-353779
Analysis Workspace： AN-348485； AN-349693； AN-357247
Analytics行動應用程式： AN-352645
分類：AN-355636、AN-355651、AN-355753、AN-356005、AN-356439、AN-356540、AN-356577、AN-356622
跨裝置分析： AN-355138
資料摘要： AN-356258； AN-357133
Data Warehouse： AN-339292； AN-353807
匯出位置：AN-356912
隱私權API： AN-352420
Report Builder： AN-352555； AN-354316
排程專案：AN-355971
區段：AN-352095；
Target報告： AN-355748

其他修正：AN-349698、AN-349880、AN-354860、AN-355355、AN-356289；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **13 個月的儲存有效期`cust_visids`** | 2024 年 8 月 20 日 | **2024 年 8 月 20 日**&#x200B;的 Analytics Hit 處理引擎版本，強制儲存期限 13 個月`cust_visids`。如果報告套裝已啟用「啟用訪客聯繫」，則此設定用於尋找 `cust_visid` (點擊 `visid_high/visid_low value` 時無 `cust_visid`)。先前，`cust_visid`( 屬於 `visid_high/visid_low`) 的對應不會過期。在此版本中，如果自點擊時 `visid_high/visid_low` 有 `cust_visid` 以來已過去 13 個月或更長時間，對應會過期。 |
| **其他實作詳細資料XDM欄位會自動對應** | 2024 年 9 月 11 日 | 使用Adobe Experience PlatformEdge Network傳送資料至Adobe Analytics時，XDM欄位`xdm.implementationdetails.name`和`xdm.implementationdetails.environment`現在一律對應到內容資料變數`c.a.x.implementationdetails.name`和`c.a.x.implementationdetails.environment`。 以前，有些情況會阻止這些值填入。 請調整任何相關的處理規則，以符合這些值的可用性。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止更新並將關閉，使用這些服務的目前整合建置將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2024 年舊版發行說明](/help/release-notes/2024.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [串流媒體收集附加元件發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新。

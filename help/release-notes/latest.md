---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d7beee25af3551426eb905f0e727545de068b2d9
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 41%

---

# 最新Adobe Analytics發行說明（2025年1月發行）

**上次更新日期**： 2024年1月22日

這些發行說明涵蓋2025年1月15日到2月中旬的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可擴展且分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在新Report Builder中排程** | 排程不僅可讓您排程新的Report Builder活頁簿。 此外，它可讓您在轉換舊版活頁簿時，擷取舊版排程工作的中繼資料。 這樣，當您將舊版活頁簿轉換為新活頁簿並排程時，您會將其傳送至與舊版活頁簿相同的電子郵件，且傳送順序相同。 [了解更多](/help/analyze/report-builder/schedule-reportbuilder.md) |  | 2025 年 1 月 22 日 |
| 在Analysis Workspace中&#x200B;**改善報告（也稱為範本）** | 報表（也稱為範本）現在提供各種改良功能：<ul><li>現在稱為[!UICONTROL 範本] （不再稱為[!UICONTROL 報表]）。</li><li>改善檢視和尋找範本的使用者體驗，包括在欄檢視或卡片檢視中檢視範本的選項。</li><li>全新的更直覺的公司範本位置(位於&#x200B;**[!UICONTROL Workspace]** > **[!UICONTROL 範本]**&#x200B;下)。</li><li>以前，在建立專案時可以從對話方塊存取公司範本。</li><li>提供其他預先建立的範本。</li></ul>[了解更多](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/templates/use-templates)。<p>管理員可以建立範本並儲存，以供登入公司的其他人使用。 [了解更多](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/templates/create-templates) | 2025年1月15日 | 2025年1月30日 |
| **交易 ID 保留期** | 2025年2月，交易ID保留期90天將延長至25個月。 `transactionID` 變數可唯一識別交易，因此點擊可繫結至透過資料來源上傳的資料。（後續檔案連結） |  | 2025年2月11日 |

## Adobe Analytics 中的修正

**A4T**： AN-355602； AN-365988
**Activity Map**： AN-365320
**Admin Console**： AN-363884
**管理工具**： AN-356747； AN-358776
**Advertising Analytics**： AN-355488
**Analysis Workspace**： AN-345318； AN-354801； AN-357052； AN-358975； AN-362886； AN-363831； AN-364124； AN-365257； AN-365319； AN-365462； AN-366194
**Analytics 1.4 API**： AN-358059
**分類**： AN-360049、AN-360424、AN-360745、AN-362208、AN-362345、AN-362560、AN-362576、AN-362633、AN-362653、AN-362762、AN-362815、AN-362881、AN-362885、AN-362973、AN-363343、AN-363558、AN-363860、AN-364239、AN-364480、AN-364451、AN-364528、AN-364548、AN-364552 AN-364585； AN-364598； AN-364643； AN-364715； AN-364912； AN-364997； AN-365081； AN-365189； AN-365197； AN-365203； AN-365431； AN-365647； AN-365794； AN-366546； AN-
**元件移轉**： AN-362236； AN-365429
**貢獻分析**： AN-360146
**資料摘要**： AN-356997、AN-362470、AN-362498、AN-362775、AN-363323、AN-363413、AN-363569、AN-364063、AN-364142、AN-364294、AN-364298、AN-364325、AN-364367、AN-364594、AN-364995、AN-365127、AN-365272、AN-365519、AN-365760、AN-366152、AN-；
**資料修復API**： AN-362773； AN-362874
**資料來源**： AN-360745； AN-362202； AN-364566
**Data Warehouse**： AN-361447； AN-362616； AN-364524； AN-365108
**行動應用程式**： AN-362856； AN-365270
**超額警報**： AN-355594； AN-364547
**平台**： AN-358914； AN-360205； AN-362990； AN-364550； AN-365454； AN-365485
**Report Builder**： AN-363478； AN-364433； AN-365610
**報告活動管理員**： AN-362440
**分段**： AN-359921
**VISTA規則**： AN-362927

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **非 Campaign 客戶將無法存取觸發程序** | 2023 年 10 月 16 日 | 在2025年1月30日，沒有Adobe Campaign授權的Adobe Analytics客戶將無法存取設定和使用[觸發器](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers)的功能。 客戶需要購買 Campaign，或計劃停止使用觸發程序，或研究提供觸發程序功能的其他 Adobe 工具。 |

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2025年1月17日 | 使用Adobe I/OJWT憑證的Adobe Analytics API和Livestream客戶必須在&#x200B;**2025年6月30日**&#x200B;前移轉至Adobe I/OOAuth伺服器對伺服器憑證。 從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Adobe Analytics API 終止更新 (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](/help/admin/c-admin-api/c-admin-14-api-eol.md)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-hant)。


## 相關資源

* [2024 年舊版發行說明](/help/release-notes/2024.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hant)
* [串流媒體收集發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新

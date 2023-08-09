---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d1b9ef79a456fc52b7fa644d088f7089c9b654e4
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 79%

---

# 目前的 Adobe Analytics 發行說明 (2023 年 8 月)

**最新更新**：2023 年 8 月 9 日

這些發行說明涵蓋2023年8月9日至9月13日的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 2023年8月9日至9月12日期間 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **API 2.0中的「分類設定」** | 提供Adobe Analytics API 2.0儲存、刪除、擷取、匯入和匯出分類集資料的方法。 | 不適用 | 2023 年 8 月 31 日 |
| **報告活動管理員** | 報告活動管理器可讓管理員詳細瞭解每個報告套裝的報告使用情況，好讓管理員在尖峰報告期間輕鬆診斷並修正容量問題。 [了解更多](/help/admin/admin/reporting-activity.md) | 不適用 | 2023 年 9 月 6 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正未載入自訂事件的問題。 (AN-324163)
* 修正無法編輯視覺效果中圖例標籤的問題。 (AN-323246)

AN-315605、AN-316306、AN-317494、AN-317844、AN-320424、AN-320597、AN-320680、AN-320869、AN-321624、AN-321693、AN-322009、AN-322244、AN-322380、AN-322432、AN-322466、AN-322556、AN-322669、AN-322735、AN-323151、AN-323220、AN-323380、AN-323492、AN-323595、AN-323755、AN-323854、AN-323916 AN-324044； AN-324200； AN-324213； AN-324238； AN-324347； AN-323598； AN-323625； AN-323631； AN-323638； AN-323641； AN-323755； AN-323767； AN-323777； AN-323825； AN-323846； AN-323972； AN-324113； AN-324170； AN-324197； AN-324273； AN-324275； AN-324345； AN-324384； AN-324433； AN-324511； AN-324513； AN-324521 AN-324524； AN-324531； AN-324532； AN-324534； AN-324537； AN-324569； AN-324618； AN-324635； AN-324688； AN-324704； AN-324712； AN-324721； AN-324745； AN-324792； AN-324793； AN-324794； AN-324795； AN-324824； AN-324905； AN-324918； AN-324932； AN-324934； AN-324947； AN-325003； AN-325073； AN-325143； AN-325148 AN-325153； AN-325177； AN-325187； AN-325252； AN-325305； AN-325363； AN-325401； AN-325439； AN-325431； AN-325491； AN-325495； AN-325508； AN-325594； AN-325601； AN-325660； AN-325779； AN-325857； AN-325883； AN-325885； AN-325886； AN-； AN-； AN-； AN-； AN-


## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **37 個月到期的購買 ID 和事件 ID (事件序列化)** | 10,2023 年 7 月 | 即將推出的 Analytics Hit 處理引擎版本，目標是在 **2023 年 7 月 13 日** 將開始強制執行 37 個月到期的購買 ID 和事件 ID (事件序列化)。目前，購買 ID 和事件 ID 在 Adob&#x200B;&#x200B;e Analytics 中為永不過期。看到/使用購買 ID 或事件 ID 後，則未來無論何時若有任何點擊，都會使該購買或事件標記為重複。隨著新處理引擎版本的推出：<ul><li>購買 ID 和事件 ID 會一律在 37 個月後到期。</li><li>如果從看到購買 ID 或事件 ID 以來已經有 37 個月，則不再將其視為重複購買或事件。</li><li> 如果您「重複使用」購買 ID 或事件 ID 已經超過 37 個月，則它們即不再被視為重複。</li></ul> |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證如需更多詳細資料和時間表，請參閱下表中的生命週期結束通知。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。在&#x200B;**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報表將自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，[!UICONTROL 發佈清單]預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.24.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

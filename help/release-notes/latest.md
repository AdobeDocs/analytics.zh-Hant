---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4134eed3cb97c478304988123196b0c906c86560
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 68%

---

# Adobe Analytics 目前發行說明 (2023 年 10 月)

**上次更新日期**：2023 年 10 月 4 日

10月發行說明涵蓋2023年10月4日至2023年10月25日的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **管理元件時可使用新的欄位** | 現在起，管理元件時可使用以下新欄位：<ul><li>使用於<p>此欄位可用於[計算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)和[區段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)。</p></li><li>上次使用<p>此欄位可用於[計算量度管理器](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)、[區段管理器](/help/components/segmentation/segmentation-workflow/seg-manage.md)以及[警報管理器](/help/components/c-alerts/alert-manager.md)。</p></li></ul><p>此資訊可協助您判斷某個元件對組織中的使用者是否有價值、其使用之處，以及是否需要刪除或修改。您可以將資料字典與此資訊搭配使用，以協助追蹤並深入了解元件在組織中的使用情況。</p> | 2023 年 9 月 20 日 | 2023 年 10 月 4 日 |
| **報告活動管理器增強功能** | 報告活動管理器可讓您查看組織中每個報告套裝的報告容量。它為管理員提供報告使用量的詳細可見度，以便在尖峰報告期間輕鬆診斷和修正產能問題。以下是報告活動管理器中現在提供的部分增強功能： <ul><li>限制後續請求：除了取消目前的請求之外，管理員現在還可以限制已定義時段內的請求。 管理員可依請求、專案和使用者限制請求。</li><li>除了使用率和容量量度之外，報告活動管理器現在還包含更多有關報告活動的資料：複雜性欄、使用者欄和連線欄。</li><li>在報告活動管理器中所做的所有取消和限制現在都顯示在稽核記錄中。 管理員可以使用稽核記錄來檢視目前取消的專案。 在報告活動管理器或稽核記錄中，取消操作無法還原。</li></ul><p>如需詳細資訊，請參閱 [報告活動管理器總覽](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 2023 年 10 月 17 日 | 2023 年 10 月 23 日 |
| **Data Warehouse 的改良功能** | 建立 Data Warehouse 要求時，您現在可以設定雲端帳戶做為報告目的地。以下雲端帳戶類型可用來傳送資料：<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>電子郵件 (此選項為先前提供)</li></ul>FTP、SFTP、Azure Blob 和 S3 仍然可用做為報告目的地，但已經不再為建議選項。<p>建立和管理 Data Warehouse 要求時的使用者體驗也有所改善。如需更多資訊，請參閱[建立 Data Warehouse 要求](/help/export/data-warehouse/create-request/t-dw-create-request.md)和[管理 Data Warehouse 要求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=zh-Hant)。 | 2023 年 9 月 12 日 | 2023 年 10 月 25 日 |
| **將 Adobe Analytics 專案及任何包含的元件移轉至 Customer Journey Analytics** | 您現在可以將 Adobe Analytics 專案移轉至 Customer Journey Analytics。此流程簡化了從 Adobe Analytics 到 Customer Journey Analytics 的轉換。 <p>您將專案移轉至 Customer Journey Analytics 時，資產會從 Adobe Analytics 報告套裝對應至 Customer Journey Analytics 資料檢視。</p> <p>您可以從 Adobe Analytics 介面將專案移轉至 Customer Journey Analytics。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | 不適用 | 2023 年 10 月 9 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正A4T報表未在Target/Analytics UI中出現的問題。 (AN-329375、AN-329745、AN-330026)

AN-313983、AN-324189、AN-325095、AN-325677、AN-325886、AN-326068、AN-326360、AN-326458、AN-327290、AN-327315、AN-327353、AN-327505、AN-327589、AN-327609、AN-327922、AN-328110、AN-328222、AN-328261、AN-328496、AN-328577、AN-328629、AN-328736、AN-328888、AN-328899、AN-328902、AN-328921 AN-328958； AN-329208； AN-329277； AN-329332； AN-329334； AN-329335； AN-329336； AN-329357； AN-329385； AN-329387； AN-329397； AN-329463； AN-329501； AN-329504； AN-329505； AN-329515； AN-329524； AN-329526； AN-329534； AN-329539； AN-329541； AN-329543； AN-329545； AN-329564； AN-329570； AN-329623； AN-329624 AN-329636； AN-329646； AN-329647； AN-329668； AN-329701； AN-329737； AN-329741； AN-329751； AN-329812； AN-329813； AN-329821； AN-329824； AN-329833； AN-329848； AN-329852； AN-329861； AN-329863； AN-329874； AN-329882； AN-329911； AN-329917； AN-329942； AN-329954； AN-329968； AN-329971； AN-329982； AN-330044 AN-330052； AN-330131； AN-330132； AN-330230； AN-330352； AN-330367； AN-330541； AN-330599

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **AdobeExperience Edge點選的完整IP模糊化** | 2023 年 9 月 27 日 | 來自Experience Edge之點選的IP模糊化功能將於2023年10月後續更新。 四月，Experience Edge新增模糊化IP位址的功能。 當時，由於Adobe Analytics處理來自Experience Edge的點選的方式，Analytics僅支援IP的部分模糊化功能。 客戶選擇Experience Edge使用完全模糊化時，Analytics只會收到部分模糊化的IP。 實作此變更時，Analytics會收到完全模糊化的IP。 |
| **Adobe Analytics Livestream - Analytics 2.0 API** | 2023 年 9 月 27 日 | 客戶現在可以存取 [Adobe Analytics直播串流的端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) 在Adobe Analytics 2.0 API底下，而不是在其先前的位置使用1.4 API。 請注意，使用Adobe I/OJWT憑證的客戶必須在2025年1月1日前移轉至Adobe I/OOAuth伺服器對伺服器憑證。 （請參閱下列EOL通知底下的詳細資訊。） |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報表和功能。支援 [!DNL Reports & Analytics] 的報表、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報告，都已自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，[!UICONTROL 發佈清單]預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.25.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

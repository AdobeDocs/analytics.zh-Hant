---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 00c6915275c4730413aa8505094886ae56649ec4
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 97%

---

# 目前的 Adobe Analytics 發行說明 (2023 年 10/11 月)

**上次更新**：2023年12月13日

這些版本注意事項涵蓋 2023 年 10 月 23 日至 2023 年 11 月底的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **報告活動管理器增強功能** | 報告活動管理器可讓您查看組織中每個報告套裝的報告容量。它為管理員提供報告使用量的詳細可見度，以便在尖峰報告期間輕鬆診斷和修正產能問題。以下是報告活動管理器中現在提供的一些增強功能： <ul><li>限制後續的請求：除了取消目前的請求之外，管理員現在還可以限制定義時段內的請求。管理員可依據請求、專案或使用者來限制請求。</li><li>除了使用情況和產能量度之外，報告活動管理器現在包括更多有關報告活動的資料：複雜度欄、使用者欄和連線欄。</li><li>現在，稽核記錄可以看到在報告活動管理員中進行的所有取消和限制。管理員可以使用稽核記錄檢視目前取消的內容。在報告活動管理器或稽核記錄中無法撤銷取消。</li></ul><p>如需詳細資訊，請參閱[報告活動管理員概觀](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 2023 年 10 月 17 日 | 2023 年 10 月 24 日 |
| **Data Warehouse 的改良功能** | 建立 Data Warehouse 要求時，您現在可以設定雲端帳戶做為報告目的地。以下雲端帳戶類型可用來傳送資料：<ul><li>Amazon S3</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>電子郵件 (此選項為先前提供)</li></ul>FTP、SFTP、Azure Blob 和 S3 仍然可用做為報告目的地，但已經不再為建議選項。<p>建立和管理 Data Warehouse 要求時的使用者體驗也有所改善。如需更多資訊，請參閱[建立 Data Warehouse 要求](/help/export/data-warehouse/create-request/t-dw-create-request.md)和[管理 Data Warehouse 要求](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html)。 | 2023 年 9 月 12 日 | 待定 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 這些分析處理和報告引擎變更將在 10 月的最後一週進行部署：我們將修復頁面或連結維度的標籤錯誤地顯示為「`Unknown`」的問題。在修復之前，當頁面名稱或連結名稱未在點擊時傳入，「`Unknown`」標籤可能會錯誤顯示，分別預設為[!UICONTROL 頁面 URL ]和[!UICONTROL 連結 URL]。這些維度設定為不區分大小寫。經過此修復，未來的報告將會是正確的。但對於歷史報告資料，某些報告結果可能仍會錯誤標記為「`Unknown`」。(AN-328030)

### 其他修正

AN-315676; AN-323398; AN-326209; AN-328178; AN-328261; AN-328395; AN-328671; AN-329282; AN-329330; AN-329355; AN-329506; AN-329516; AN-329738; AN-329769; AN-329771; AN-329816; AN-329877; AN-329928; AN-329957; AN-329962; AN-329966; AN-330023; AN-330081; AN-330083; AN-330105; AN-330138; AN-330140; AN-330165; AN-330241; AN-330359; AN-330366; AN-330427; AN-330438; AN-330442; AN-330534; AN-330616; AN-330654; AN-330783; AN-330879; AN-330881; AN-330883; AN-330887; AN-330888; AN-330955; AN-330979; AN-331031; AN-331053; AN-331068; AN-331071; AN-331074; AN-331075; AN-331076; AN-331078; AN-331085; AN-331093; AN-331167; AN-331171; AN-331181; AN-331196; AN-331226; AN-331258; AN-331260; AN-331279; AN-331286; AN-331290; AN-331365; AN-331375; AN-331376; AN-331454; AN-331519; AN-331570; AN-331590; AN-331593; AN-331603; AN-331751; AN-331816; AN-331897; AN-331900; AN-331906; AN-331926; AN-331929; AN-332031; AN-332067; AN-332101; AN-332114; AN-332156; AN-332201; AN-332225; AN-332253; AN-332277; AN-332361; AN-332370; AN-332386

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **Adobe Experience Edge 點擊的完整 IP 模糊化** | 2023 年 9 月 27 日 | 來自 Experience Edge 點擊的 IP 模糊化將於 2023 年 10 月之後更新。在 2023 年 4 月，Experience Edge 新增了模糊 IP 位址的功能。當時，由於 Analytics 處理來自 Experience Edge 點擊的方式，Adobe Analytics 僅支援 IP 的部分模糊化。客戶選擇 Experience Edge 的完全模糊化時，Analytics 僅收到部分模糊的 IP。實施此變更後，Analytics 將收到完全模糊化的 IP。 |
| **Adobe Analytics Livestream - Analytics 2.0 API** | 2023 年 9 月 27 日 | 客戶現在可以存取 [Adobe Analytics Livestream 端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/)，就在 Adobe Analytics 2.0 API 之下，而不是其先前 1.4 API 的位置。請注意，使用 Adobe I/O JWT 認證的客戶必須在 2025 年 1 月 1 日之前移轉到 Adobe I/O OAuth Server-to-Server 認證。(請參閱以下 EOL 通知中的詳細資訊。) |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** EOL | 2023年12月13日 | 有效 **2024年1月17日**，Adobe打算停止 [!DNL Reports & Analytics] 及其隨附的報告和功能。 支援 [!DNL Reports & Analytics] 的報表、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報告，都已自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2023年12月13日 | 作為Reports &amp; Analytics EOL的一部分， [!UICONTROL 發佈清單] 即將結束生命週期的日期 **2024年1月17日**. 您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.25.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

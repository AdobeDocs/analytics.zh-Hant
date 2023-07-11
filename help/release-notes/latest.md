---
title: 最新 Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4c6b05ba46e1e5d7bfca24d8cad57fd4479ed8fa
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 76%

---

# 目前的 Adobe Analytics 發行說明 (2023 年 7 月)

**上次更新日期**：2023 年 7 月 11 日

Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **設定雲端帳戶存放區位置以擷取分類資料** | 您現在可以管理用於分類集自動化的雲端帳戶儲存位置。<p> | 不適用 | 2023 年 7 月 10 日 |
| **資料修復篩選增強功能** | 「資料修復」新增了三項篩選改善功能：<ul><li>依一個變數篩選以修改第二個變數。 例如，如果 `eVar2` 包含「@」，然後刪除 `eVar3`.</li><li>篩選數值或非數值</li><li>使用AND套用多個篩選器。 例如，其中 `eVar2="a"` 和 `eVar3="b"`</li></ul>[了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **資料摘要匯出的安全目標** | 現在可以將資料摘要傳送到以下雲端儲存空間目標：<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>不再建議使用以前提供的目標 (FTP、SFTP、S3 和 Azure Blob)。[了解更多](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=zh-Hant) | 2023 年 6 月 12 日 | 2023 年 7 月 15 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

AN-307816、AN-318111、AN-318584、AN-318828、AN-320440、AN-320568、AN-320616、AN-321013、AN-321513、AN-321520、AN-321757、AN-321820、AN-321917、AN-322034、AN-322135、AN-322140、AN-322142、AN-322251、AN-322353、AN-322378、AN-322383、AN-322427、AN-322458、AN-322543、AN-322630、AN-322637 AN-322638； AN-322647； AN-322728； AN-322732； AN-322777； AN-322817； AN-322957； AN-322958； AN-323035； AN-323074； AN-323150； AN-323196； AN-323197； AN-323205； AN-323206； AN-323217； AN-323224； AN-323225； AN-323244； AN-323257； AN-323277； AN-323280； AN-323293； AN-323309； AN-323318； AN-323468； AN-323476 AN-323514； AN-323572； AN-323592； AN-323782； AN-323835

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **37 個月到期的購買 ID 和事件 ID (事件序列化)** | 10,2023 年 7 月 | 即將發行的Analytics點選處理引擎將於以下日期發行 **2023年7月13日**，將開始強制執行「購買ID」和「事件ID」 （事件序列化）的有效期37個月。 目前，購買 ID 和事件 ID 在 Adob&#x200B;&#x200B;e Analytics 中為永不過期。看到/使用購買 ID 或事件 ID 後，則未來無論何時若有任何點擊，都會使該購買或事件標記為重複。隨著新處理引擎版本的推出：<ul><li>購買 ID 和事件 ID 會一律在 37 個月後到期。</li><li>如果從看到購買 ID 或事件 ID 以來已經有 37 個月，則不再將其視為重複購買或事件。</li><li> 如果您「重複使用」購買 ID 或事件 ID 已經超過 37 個月，則它們即不再被視為重複。</li></ul> |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證如需更多詳細資料和時間表，請參閱下表中的生命週期結束通知。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉至Adobe I/OOAuth伺服器對伺服器認證** | 2023 年 5 月 11 日 | 使用Adobe I/OJWT憑證的Adobe Analytics API和Livestream客戶必須移轉至Adobe I/OOAuth伺服器對伺服器憑證，遷移方式為 **2025年1月1日**. Adobe I/O自2024年5月1日起不允許建立新的JWT認證。 使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用OAuth的新舊應用程式實作指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** EOL | 2023 年 3 月 7 日 | 自 **2023 年 12 月 31 日**&#x200B;起生效，Adobe 計畫停止支援 [!DNL Reports & Analytics] 及其隨附的報告和功能。支援 [!DNL Reports & Analytics] 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。在&#x200B;**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報表將自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **結束[!UICONTROL 發佈清單] 功能生命週期** | 2022 年 9 月 29 日 | 作為 Reports &amp; Analytics EOL 的一部分，[!UICONTROL 發佈清單]預定在 **2023 年 12 月**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **Data Workbench 的 EOL** | 2022 年 9 月 14 日 | Adobe 打算自 **2023 年 12 月 31 日** 起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=zh-Hant)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.23.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2022 年舊版發行說明](/help/release-notes/2022.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

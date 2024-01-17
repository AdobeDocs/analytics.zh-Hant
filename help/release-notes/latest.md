---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c3f59a07d51f5e6a73fa87aed573450c133d5bd6
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 50%

---

# 最新 Adobe Analytics 版本注意事項 (2024 年 1 月)

**上次更新**：2024年1月10日

這些發行說明涵蓋2024年1月至2024年2月13日的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouse 更新** | 現在可以使用以下 Data Warehouse 改良功能：<ul><li>在建立 Data Warehouse 請求時，使用者現在可以啟用名為「[!UICONTROL **設為可供您組織中使用者所使用**]」的新切換，讓組織中的所有使用者都可以使用請求。<p>有關詳細資訊，請參閱 [Data Warehouse 請求一般設定](/help/export/data-warehouse/create-request/dw-general-settings.md)。</p></li><li>在建立或管理 Data Warehouse 報表目的地時，系統管理員現在可以啟用名為「[!UICONTROL **顯示所有目的地**]」的切換，用來顯示組織中使用者建立的帳戶和位置。<p>有關詳細資訊，請參閱[為 Data Warehouse 請求設定報告目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。</p></li> | 不適用 | 2024 年 1 月 10 日 |
| **關鍵量度摘要視覺效果的更新** | 使用「關鍵量度摘要」視覺效果時，比較日期範圍現在可以根據您選擇的「比較日期範圍」選項是相對於主要日期範圍還是固定日期範圍自動更新。 [了解更多](/help/analyze/analysis-workspace/visualizations/key-metric.md)。 | 不適用 | 2024年1月17日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正下列分類問題：AN-314821、AN-326839、AN-332079、AN-332704、AN-332812、AN-332902、AN-332975、AN-333300、AN-333023、AN-333033、AN-333174、AN-333910、AN-334097、AN-334208、AN-334373、AN-334439、AN-334698、AN-334838、AN-334848、AN-334987、AN-335046、AN-335082、AN-335202、AN-335203、AN-335254 an-335322； AN-335552； AN-335591； AN-335603； AN-335610； AN-335617； AN-335699； AN-335891； AN-335901； AN-336063； AN-336072； AN-336193； AN-336479； AN-336684； AN-336801； AN-337370； AN-337398； AN-； AN-； AN-； AN-； AN-； AN-； AN-
* 修正下列分類規則產生器問題：AN-332390、AN-332573、AN-332718、AN-332927、AN-333248、AN-333953、AN-334647、AN-334736、AN-334910、AN-335642、AN-335683、AN-335811、AN-336033、AN-336569、AN-336852、AN-336875、AN-336902、AN-337190、AN-、AN-；
* 修正下列A4T問題：AN-334564、AN-336178；
* 已修正下列伺服器呼叫使用量問題：AN-332568、AN-333105、AN-333167、AN-333983、AN-334209、AN-334278
* 修正下列Data Warehouse問題：AN-333010、AN-333076、AN-330227、AN-331580、AN-333350、AN-334291、AN-334283、AN-334287、AN-334301、AN-334385、AN-334453、AN-334977、AN-335079、AN-335171、AN-335245、AN-335426、AN-335680、AN-335818、AN-336087、AN-337308、AN-、AN-、AN-、AN-；
* 修正下列資料摘要問題：AN-332241、AN-332366、AN-332617、AN-332654、AN-332702、AN-332723、AN-333014、AN-333166、AN-334037、AN-334125、AN-334211、AN-334216、AN-334235、AN-334976、AN-335158、AN-335368、AN-335408、AN-335468、AN-335471、AN-335528、AN-335596、AN-335662、AN-335733、AN-335883、AN-335894 AN-335968； AN-336098； AN-336192； AN-336243； AN-336659； AN-336977； AN-337117； AN-337219； AN-337262； AN-337393； AN-337462； AN-337854； AN-； AN-； AN-
* 修正下列Report Builder問題：AN-335246、AN-336311；
* 修正下列Analysis Workspace問題：AN-323760、AN-324191、AN-324913、AN-330126、AN-332808、AN-333168、AN-333382、AN-334839、AN-336040、AN-337043；

### 其他修正

AN-323975、AN-325383、AN-325809、AN-326787、AN-331611、AN-331818、AN-332124、AN-332272、AN-332911、AN-333070、AN-333302、AN-333377、AN-333904、AN-333928、AN-333968、AN-334056、AN-334099、AN-334191、AN-334207、AN-334776、AN-335206、AN-335294、AN-335320、AN-335394、AN-335443、AN-335967 -336099； AN-337452； AN-337463

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| 新增AdobeAPI物件成員 | 2024年1月17日 | Adobe可將選用的請求和回應成員（名稱/值組）新增到現有API物件，而不需要通知或變更版本設定。 這類新增專案應該是實施作業的不間斷變更。 Adobe建議您參考與API整合的協力廠商工具的API檔案，以便在處理時若無法瞭解這類新增內容，將予以忽略。 若未先透過發行說明提供標準通知，Adobe將不會移除引數或新增必要引數。 |
| `getPageLoadTime` 外掛程式已棄用 | 2024 年 1 月 10 日 | 此外掛程式已不再受支援。 其程式碼會使用performance.timing方法，根據MDN，該方法已 [已棄用](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). 已啟動更新外掛程式的工作。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** EOL | 2024 年 1 月 10 日 | **2024 年 1 月 17 日**&#x200B;起，Adobe 打算停止支援 [!DNL Reports & Analytics] 及其隨附的報表和功能。支援 [!DNL Reports & Analytics] 的報表、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 [!DNL Reports & Analytics] 功能在 [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant) 中都有提供。自 Analysis Workspace 在 2015 年發佈以來，[!DNL Reports & Analytics] 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。[本通知](https://spark.adobe.com/page/6WnF8JK6IRDhf/)說明生命週期結束流程。<p>在 2023 年 12 月 31 日，我們將終止許多關聯的 Reports and Analytics 功能，包括但不限於：排程報表、資料擷取和 DL 報表。2023 年 12 月 31 日之後，將不再傳送任何排程報表。**2023 年 4 月**，任何排程在 2023 年 12 月 31 日之後到期的報告，都已自動更新並恢復到 2023 年 12 月 31 日到期。此外，您不能再排程 2023 年 12 月 31 日之後的未來報表。 |
| **結束[!UICONTROL 發佈清單]功能生命週期** | 2024 年 1 月 10 日 | 作為 Reports &amp; Analytics EOL 的一部分，[!UICONTROL 發佈清單]預定在 **2024 年 1 月 17 日**&#x200B;結束生命週期。您將無法建立新的發佈清單或存取現有[!UICONTROL 發佈清單]，來傳送或排程 [!UICONTROL Analysis Workspace] 專案。 |
| **Data Workbench 的 EOL** | 2024 年 1 月 2 日 | Adobe 自 **2023 年 12 月 31 日**&#x200B;起終止 Data Workbench 的服務。請參閱 [Data Workbench 生命週期結束通知](https://express.adobe.com/page/GSu6oKOD88GAj/)以取得詳細資料。若有任何問題，請聯絡貴組織的 Adobe 客戶經理。 |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.25.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2023 年舊版發行說明](/help/release-notes/2023.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

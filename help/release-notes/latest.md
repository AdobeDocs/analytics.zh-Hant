---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: efe0f96db6a65389c94faf4f8d24b026e53a403c
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 99%

---

# Adobe Analytics 目前的發行說明 (2024 年 2 月)

**上次更新日期**：2024 年 2 月 21 日

這些發行說明涵蓋 2024 年 2 月 14 日至 2024 年 3 月 11 日的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurement更新** | [AppMeasurement版本2.26.0](/help/implement/appmeasurement-updates.md) 可用。 | | 2024年3月4日 |
| **Data Warehouse 更新** | 現在可以使用以下 Data Warehouse 改良功能：<ul><li>在建立 Data Warehouse 請求時，使用者現在可以啟用名為「[!UICONTROL **設為可供您組織中使用者所使用**]」的新切換，讓組織中的所有使用者都可以使用請求。<p>有關詳細資訊，請參閱 [Data Warehouse 請求一般設定](/help/export/data-warehouse/create-request/dw-general-settings.md)。</p></li><li>在建立或管理 Data Warehouse 報表目的地時，系統管理員現在可以啟用名為「[!UICONTROL **顯示所有目的地**]」的切換，用來顯示組織中使用者建立的帳戶和位置。<p>有關詳細資訊，請參閱[為 Data Warehouse 請求設定報告目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)。</p></li> | 不適用 | 2024 年 1 月 10 日 |
| **關鍵量度摘要視覺效果更新** | 使用關鍵量度摘要視覺效果時，比較日期範圍現在可以自動更新，具體取決於您選擇的比較日期範圍選項是相對於主要日期範圍還是固定的。[了解更多](/help/analyze/analysis-workspace/visualizations/key-metric.md)。 | 不適用 | 2024 年 1 月 17 日 |
| **Data Warehouse API 文件** | 請參閱「[Adobe Analytics Data Warehouse API 2.0](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Warehouse%20APIs#/Data%20Warehouse%20Scheduled%20Requests%20API)」以了解更多。前往「[!UICONTROL 選取一個定義]」，並選取「[!UICONTROL Data Warehouse API]」。 | | 2024 年 2 月 19 日 |
| **Web SDK 的 Activity Map，無需額外費用** | 目前，Activity Map 連結事件被視為是其本身事件並會產生額外費用。此增強功能會產生一些連結事件，並將這些事件封裝至下一個點擊中，類似於 AppMeasurement 處理事件的方式。 |  | 2024 年 3 月 6 日 |
| **提高預設低流臨界值** | 在 **2024 年 4 月中旬**，Adobe 將開始提高預設報告套裝低流量臨界值，如下所示： ![低流量臨界值](assets/thresholds.png) 這只會影響目前設定低於新臨界值的變數。這些改變將逐步進行，我們預計這項工作將在&#x200B;**五月底**&#x200B;結束。隨著這些增加的推出，您可能會注意到高基數變數的變化：<ul><li>更多維度值可用於報告。</li><li>區段和計算量度可能包含更多資料。</li><li>以區段為主的虛擬報告套裝可能包含更多資料。</li><li>分類匯出可能包含更多資料。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月下旬 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正了以下分類問題：AN-319515；AN-337559；AN-338149；AN-338702；AN-338769；AN-338891；AN-339327；AN-339649；AN-339668；AN-339669；AN-339776；AN-339822；AN-340017；AN-340202；AN-340476；
* 修正了以下分類規則產生器問題：AN-338385；AN-338399；AN-338592；AN-338810；AN-338893；AN-339431；AN-339894；AN-339933；AN-340201；AN-340309；
* 修正了以下 A4T 問題：AN-334830；AN-336194；AN-338309；AN-338650；
* 修正了以下資料收集問題：AN-339323
* 修正了以下 Data Warehouse 問題：AN-335542；AN-331425；AN-337215；AN-338445；AN-338643；AN-338651；AN-339461；AN-340066；AN-340207；AN-340460
* 修正了以下資料摘要問題：AN-335952；AN-338653；AN-339508；AN-339681；AN-340418
* 修正了以下資料來源問題：AN-338648
* 修正了以下 Analysis Workspace 問題：AN-326509；AN-336186；AN-336190；AN-336309；AN-337922；AN-338094；AN-338323；AN-338556；AN-339600；AN-340445

### Analytics 其他修正

AN-328239；AN-332908；AN-335449；AN-335517；AN-336075；AN-336100；AN-336128；AN-338088；AN-338270；AN-338393；AN-338494；AN-339326；AN-339742；AN-339883；AN-340419；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| Adobe API 物件會員新增 | 2024 年 1 月 17 日 | Adobe 可能會為現有 API 物件隨時新增選擇性請求和回應會員 (名稱/值對)，恕不另行通知或變更版本設定。Adobe 建議您參考與我們的 API 整合的任何協力廠商工具的 API 文件，以便在不理解的情況下在處理過程中忽略此類新增。如果實施得當，此類新增對於您的實施來說是非破壞性的變更。Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |
| `getPageLoadTime` 外掛程式已過時 | 2024 年 1 月 10 日 | 不再支援此外掛程式。其程式碼使用了 performance.timing 方法，該方法 (根據 MDN) 已[過時](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)。已經開始更新外掛程式的工作。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.25.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2023 年舊版發行說明](/help/release-notes/2023.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

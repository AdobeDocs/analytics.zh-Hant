---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 55c08fd64b2fbac0e21af10896773c2530fa64a8
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 42%

---

# Adobe Analytics 目前的發行說明 (2024 年 2 月)

**上次更新**：2024年2月14日

這些發行說明涵蓋2024年2月14日至2024年3月11日的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Web SDKActivity Map，不需額外付費** | 目前，Activity Map連結事件會計為自己的事件，並產生額外費用。 此增強功能會擷取一些連結事件，並將它們封裝到下一次點選中，類似於AppMeasurement處理事件的方式。 |  | 2024年2月14日 |
| **增加預設低流量臨界值** | 在 **2024年4月中旬**，Adobe將會開始增加預設報表套裝的低流量臨界值，如下所示： ![低流量臨界值](assets/thresholds.png) 這只會影響目前設定在新的臨界值以下的變數。 這些變更將以漸進方式進行，我們預計工作將由 **5月底**. 隨著這些增加的推出，您可能會注意到高基數變數的變更：<ul><li>可能有更多維度值可用於報表。</li><li>區段和計算量度可能包含更多資料。</li><li>以區段為基礎的虛擬報表套裝可能包含更多資料。</li></ul> | 2024年4月中旬 | 2024年5月底 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正下列分類問題：AN-319515、AN-337559、AN-338149、AN-338702、AN-338769、AN-338891、AN-339327、AN-339649、AN-339668、AN-339669、AN-339776、AN-339822、AN-340017、AN-340202、AN-340476；
* 修正下列分類規則產生器問題：AN-338385、AN-338399、AN-338592、AN-338810、AN-338893、AN-339431、AN-339894、AN-339933、AN-340201、AN-340309；
* 修正下列A4T問題：AN-334830、AN-336194、AN-338309、AN-338650；
* 已修正下列資料收集問題： AN-339323
* 修正下列Data Warehouse問題：AN-335542、AN-331425、AN-337215、AN-338445、AN-338643、AN-338651、AN-339461、AN-340066、AN-340207、AN-340460
* 已修正下列資料摘要問題： AN-335952、AN-338653、AN-339508、AN-339681、AN-340418
* 修正下列資料來源問題： AN-338648
* 修正下列Analysis Workspace問題：AN-326509、AN-336186、AN-336190、AN-336309、AN-337922、AN-338094、AN-338323、AN-338556、AN-339600、AN-340445

### Analytics 其他修正

AN-328239、AN-332908、AN-335449、AN-335517、AN-336075、AN-336100、AN-336128、AN-338088、AN-338270、AN-338393、AN-338494、AN-339326、AN-339742、AN-339883、AN-340419；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| Adobe API 物件會員新增 | 2024 年 1 月 17 日 | Adobe可隨時將選用的請求和回應成員（名稱/值配對）新增至現有的API物件，而不需通知或變更版本設定。 Adobe建議您參考與API整合的協力廠商工具的API檔案，以便在處理時忽略這類新增專案（如果未瞭解這些專案）。 如果正確實作，這類新增內容對您的實作而言為不中斷的變更。 Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |
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

---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 416725e01f469e3fafc1d52971535ab63e998f5f
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 42%

---

# Adobe Analytics 目前的版本注意事項 (2024 年 3 月)

**上次更新**：2024年3月13日

這些發行說明涵蓋2024年3月12日至2024年4月的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurement 更新** | [AppMeasurement 版本 v2.26.0](/help/implement/appmeasurement-updates.md) 現已推出。 | | 2024 年 3 月 4 日 |
| **「專案」登陸頁面上可用的新欄** | 此 **[!UICONTROL 上次使用日期]** 現在當您在檢視專案標籤時 [Adobe Analytics登陸頁面](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html). <p>此資訊可顯示專案上次開啟的日期和時間，以協助您判斷專案是否對貴組織中的使用者有用。</p> <p>先前， **[!UICONTROL 上次使用日期]** 欄僅在計算量度管理員、區段管理員和警報管理員中可用。</p> |  | 2024 年 3 月 13 日 |
| **Analytics支援Google所需的DMA同意標幟** | 由於新的歐洲隱私權法規，Google要求歐洲收集的資料若已傳送給他們，必須指出是否已授予兩種特定型別的同意。 **從3月6日開始**，Google將不再接受無法指出已獲授相關同意的事件資料。 Adobe Analytics已發行支援，可透過新的adConsent變數擷取此資料。 您可以在中看到新變數已列出 [隱私權報表UI](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). 如果您想要啟用此專案，而且先前同意的變數已啟用隱私權，您將需要重新啟用隱私權。 |  | 2024 年 3 月 13 日 |
| **計算量度管理員和區段管理員中「使用位置」欄包含的Report Builder使用情形** | 檢視 **使用位置** 欄（位於計算量度管理員或區段管理員中），現在已可為Report Builder使用資料。<p>以往，「區段管理器」中的使用情況資料僅適用於「警報」、「專案」、「已排程專案」和「計算量度」；而「計算量度管理器」中的使用情況資料僅適用於「警報」、「專案」和「已排程專案」。</p> |  | 3月底或4月初 |
| **對資料摘要、Data Warehouse和分類集使用相同的雲端帳戶** | 您建立的雲端帳戶和位置現在可用於匯出資料(搭配資料摘要和Data Warehouse)和匯入資料（搭配分類集）。<p> **設定帳戶時的變更：** 使用者可以設定雲端匯入和匯出帳戶，以及設定雲端匯入和匯出位置，這些位置可用於以下任一用途：<ul><li>使用分類集匯入資料</li><li>使用資料摘要匯出資料</li><li>使用Data Warehouse匯出資料。</li></ul><p>**管理帳戶時的變更**：使用者可使用「位置」頁面（在「元件>位置」下方）來檢視及管理其建立的所有帳戶和位置，無論其建立於何處。 <p>以前，「位置」頁面僅套用至為匯入具有「分類設定」的資料而建立的帳戶。</p> | | 2024 年 4 月 |
| **管理員可以管理其組織中的所有位置** | 「位置」頁面上的新選項可讓管理員檢視及管理組織中的所有位置。 <p>以前，管理員只能檢視和管理他們建立的位置。</p> |  | 2024 年 4 月 |
| **Activity Map對Web SDK使用的伺服器呼叫較少** | 目前，Activity Map連結事件會計為自己的事件，並產生額外費用。 <p>此增強功能會產生一些連結事件，並將這些事件封裝至下一個點擊中，類似於 AppMeasurement 處理事件的方式。</p> |  | 2024 年 4 月 3 日 |
| **提高預設低流臨界值** | 在 **2024 年 4 月中旬**，Adobe 將開始提高預設報告套裝低流量臨界值，如下所示： ![低流量臨界值](assets/thresholds.png) 這只會影響目前設定低於新臨界值的變數。這些改變將逐步進行，我們預計這項工作將在&#x200B;**五月底**&#x200B;結束。隨著這些增加的推出，您可能會注意到高基數變數的變化：<ul><li>更多維度值可用於報告。</li><li>區段和計算量度可能包含更多資料。</li><li>以區段為主的虛擬報告套裝可能包含更多資料。</li><li>分類匯出可能包含更多資料。</li></ul> | | 2024 年 4 月中旬 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正下列分類問題：AN-335632、AN-337559、AN-340164、AN-340370、AN-341089、AN-341211、AN-341284、AN-341469、AN-341481、AN-341760、AN-341778、AN-342144、AN-342258、AN-342338、AN-342400
* 修正下列分類規則產生器問題：AN-340921、AN-341269、AN-341292、AN-341467、AN-341666、AN-342145、AN-342329
* 修正下列智慧型警報問題： AN-340736
* 修正下列區段問題： AN-336242
* 修正下列Data Warehouse問題：AN-335354、AN-339446、AN-339774、AN-340221、AN-340599、AN-341277、AN-342009、AN-342088、AN-342592
* 已修正下列資料摘要問題： AN-335508、AN-340887、AN-341050、AN-341208、AN-341403、AN-341479、AN-341524、AN-341661、AN-342000、AN-342125、AN-342256、AN-342301、AN-342410、AN-342502、AN-342525
* 已修正下列Report Builder問題： AN-340540
* 修正下列Analysis Workspace問題：AN-295889、AN-330981、AN-338818、AN-339730、AN-341114、AN-341520；

### Analytics 其他修正

AN-312198、AN-338009、AN-339549、AN-333970、AN-334790、AN-336461、AN-336572、AN-339549、AN-341119、AN-341246、AN-341268、AN-341272、AN-341475、AN-341547、AN-341558、AN-341680、AN-342017；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **新增AdobeAPI物件成員** | 2024 年 1 月 17 日 | Adobe 可能會為現有 API 物件隨時新增選擇性請求和回應會員 (名稱/值對)，恕不另行通知或變更版本設定。Adobe 建議您參考與我們的 API 整合的任何協力廠商工具的 API 文件，以便在不理解的情況下在處理過程中忽略此類新增。如果實施得當，此類新增對於您的實施來說是非破壞性的變更。Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |
| **`getPageLoadTime`外掛程式已棄用** | 2024 年 1 月 10 日 | 不再支援此外掛程式。其程式碼使用了 performance.timing 方法，該方法 (根據 MDN) 已[過時](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)。已經開始更新外掛程式的工作。 |

{style="table-layout:auto"}

## 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **移轉到 Adobe I/O OAuth Server-to-Server 認證** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 認證的 Adobe Analytics API 和 Livestream 客戶必須在 **2025 年 1 月 1 日**&#x200B;之前移轉到 Adobe I/O OAuth Server-to-Server 認證從 2024 年 5 月 1 日開始，Adobe I/O 將不允許建立新的 JWT 認證。使用 JWT 的客戶必須建立新的 OAuth Server-to-Server 認證，或將他們現有的 JWT 認證移轉到 OAuth Server-to-Server 認證。客戶還必須更新他們的用戶端應用程式，才能使用新的 OAuth Server-to-Server 認證。 <ul><li>[從 Service Account (JWT) 認證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth 新舊應用程式的實施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[使用新的 OAuth Server-to-Server 認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常見問題集](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2023 年舊版發行說明](/help/release-notes/2023.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

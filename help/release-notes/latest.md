---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b5d274b6b529737b2ad1d135599fe0b0dcf4bf2a
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 86%

---

# Adobe Analytics 目前的發行說明 (2024 年 3 月)

**上次更新**：2024年3月21日

這些發行說明涵蓋 2024 年 3 月 12 日至 2024 年 4 月的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurement 更新** | [AppMeasurement 版本 v2.26.0](/help/implement/appmeasurement-updates.md) 現已推出。 | | 2024 年 3 月 4 日 |
| **專案登陸頁面珼在提供新欄** | 現在，在 [Adobe Analytics 登陸頁面](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html)上檢視「專案」標籤時，會提供&#x200B;**[!UICONTROL 「上次使用」]**&#x200B;欄。 <p>這項資訊可顯示專案上次開啟的日期和時間，幫助您確定專案對您組織中的使用者是否重要。</p> <p>以前，**[!UICONTROL 「上次使用」]**&#x200B;欄只適用於計算量度管理器、區段管理器以及警報管理器。</p> |  | 2024 年 3 月 13 日 |
| **Analytics 支援 Google 要求取得 DMA 的同意標籤** | 由於新的歐洲隱私權法規，Google 要求在歐洲收集並發送給他們的資料必須表明是否取得兩種特定類型的同意授權。 **從 3 月 6 日開始**，Google 將不再接受未表明是否已獲得相關同意授權的事件資料。Adobe Analytics 已發布對透過新的 adConsent 變數擷取此資料的支援。您可以看到[隱私權報告 UI](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) 中所列的新變數。如果您想啟動此功能並且已經為先前的同意變數啟用隱私權，則您將需要再次啟用隱私權。<p>此 [廣告平台同意維度](/help/components/dimensions/ad-consent.md) 顯示是否收集同意將資料傳送至Google等協力廠商廣告提供者。 |  | 2024 年 3 月 13 日 |
| **Report Builder 使用情況包含在計算量度管理器和區段管理器的「使用於」欄中** | 現在，在計算量度管理器或區段管理器中檢視「**使用於**」欄時，可以看到 Report Builder 使用情況資料。<p>之前，區段管理器僅提供警報、專案、已排程專案和計算量度的使用情況資料；而計算量度管理器僅提供警報、專案、已排程專案的使用情況資料。</p> |  | 三月底或四月初 |
| **為資料摘要、Data Warehouse 和分類集使用相同的雲端帳戶** | 您建立的雲端帳戶和位置現在可用來匯出資料 (使用資料摘要和 Data Warehouse) 並匯入資料 (使用分類集)。<p> **設定帳戶時的變更：** 使用者可以設定雲端匯入和匯出帳戶，以及設定可用於以下任意目的雲端匯入和匯出位置：<ul><li>使用分類集匯入資料</li><li>使用資料來源匯出數據</li><li>使用 Data Warehouse 匯出資料。</li></ul><p>**管理帳戶時的變更**：使用者可以使用「位置」頁面 (在「元件 > 位置」下) 來查看和管理他們建立的所有帳戶和位置，無論這些是在何處建立。 <p>以前，「位置」頁面僅適用於為使用分類集匯入資料而建立的帳戶。</p> | | 2024 年 4 月 |
| **管理員可以管理其組織中的所有位置和帳戶** | 「位置」標籤（在「元件>位置」頁面上）上的新選項可讓管理員檢視及管理組織中的所有位置。<p>「位置」帳號標籤（在「元件>位置」頁面上）上的新選項可讓管理員檢視及管理組織中的所有帳號。</p> <p>以前，管理員只能檢視和管理他們建立的位置和帳戶。</p> |  | 2024 年 4 月 |
| **Activity Map 使用更少的 Web SDK 伺服器呼叫** | 目前，Activity Map 連結事件被視為是其本身事件並會產生額外費用。 <p>此增強功能會產生一些連結事件，並將這些事件封裝至下一個點擊中，類似於 AppMeasurement 處理事件的方式。</p> |  | 2024年4月30日 |
| **提高預設低流臨界值** | 在 **2024 年 4 月中旬**，Adobe 將開始提高預設報告套裝低流量臨界值，如下所示： ![低流量臨界值](assets/thresholds.png) 這只會影響目前設定低於新臨界值的變數。這些改變將逐步進行，我們預計這項工作將在&#x200B;**五月底**&#x200B;結束。隨著這些增加的推出，您可能會注意到高基數變數的變化：<ul><li>更多維度值可用於報告。</li><li>區段和計算量度可能包含更多資料。</li><li>以區段為主的虛擬報告套裝可能包含更多資料。</li><li>分類匯出可能包含更多資料。</li></ul> | | 2024 年 4 月中旬 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正以下分類問題：AN-335632；AN-337559；AN-340164；AN-340370；AN-341089；AN-341211；AN-341284；AN-341469；AN-341481；AN-341760；AN-341778；AN-342144；AN-342258；AN-342338；AN-342400
* 修正以下分類規則產生器問題：AN-340921；AN-341269；AN-341292；AN-341467；AN-341666；AN-342145；AN-342329
* 修正以下智慧型警報問題：AN-340736
* 修正以下分段問題：AN-336242
* 修正了以下 Data Warehouse 問題：AN-335354；AN-339446；AN-339774；AN-340221；AN-340599；AN-341277；AN-342009；AN-342088；AN-342592
* 修正了以下資料摘要問題：AN-335508；AN-340887；AN-341050；AN-341208；AN-341403；AN-341479；AN-341524；AN-341661；AN-342000；AN-342125；AN-342256；AN-342301；AN-342410；AN-342502；AN-342525
* 修正以下 Report Builder 問題：AN-340540
* 修正以下 Analysis Workspace 問題：AN-295889；AN-330981；AN-338818；AN-339730；AN-341114；AN-341520；

### Analytics 其他修正

AN-312198、AN-338009、AN-339549、AN-333970、AN-334790、AN-336461、AN-336572、AN-339549、AN-341119、AN-341246、AN-341268、AN-341272、AN-341475、AN-341547、AN-341558、AN-341680、AN-342017；

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **已儲存的13個月到期`cust_visids`** | 2024年3月20日 | 即將發行的Analytics點選處理引擎預定在4月或5月發行，將開始強制執行13個月的儲存有效期 `cust_visids`. 如果報表套裝已啟用「啟用訪客聯絡」，此設定會用於尋找 `cust_visid` 針對 `visid_high/visid_low value` 不含 `cust_visid` 在點選上。 目前，的對應沒有到期日 `cust_visid` 針對 `visid_high/visid_low`. 在此版本中，如果自以下時間以來已過13個月或更久 `visid_high/visid_low` 曾經 `cust_visid` 在點選上，對應將會過期。 |
| **Adobe API 物件會員新增** | 2024 年 1 月 17 日 | Adobe 可能會為現有 API 物件隨時新增選擇性請求和回應會員 (名稱/值對)，恕不另行通知或變更版本設定。Adobe 建議您參考與我們的 API 整合的任何協力廠商工具的 API 文件，以便在不理解的情況下在處理過程中忽略此類新增。如果實施得當，此類新增對於您的實施來說是非破壞性的變更。Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |
| **`getPageLoadTime`外掛程式已過時** | 2024 年 1 月 10 日 | 不再支援此外掛程式。其程式碼使用了 performance.timing 方法，該方法 (根據 MDN) 已[過時](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming)。已經開始更新外掛程式的工作。 |

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

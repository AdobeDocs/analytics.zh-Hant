---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7468463e2fe1de16221b4528919b6abd6c8aedcb
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 43%

---

# Adobe Analytics 目前的版本注意事項 (2024 年 4 月)

**上次更新**：2024年4月17日

這些發行說明涵蓋2024年4月17日至5月的發行期間。 Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **串流媒體：將Roku資料傳送至Adobe Experience PlatformEdge Network** | 現在，當 [使用Experience Platform Edge安裝Media Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)，您可以使用Adobe Experience Platform Roku SDK傳送串流媒體資料給Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **改善Web SDK移轉的工作流程** | 資料串流現在會自動將Web SDK資料物件的欄位直接對應到Adobe Analytics。 [資料物件對應](/help/implement/aep-edge/data-var-mapping.md) 類似 [XDM物件對應](/help/implement/aep-edge/xdm-var-mapping.md)，但不需要XDM結構描述。 此改良的工作流程提供下列優點：<ul><li>這會延遲使用結構描述的需求，直到您準備好將資料傳送至Adobe Experience Platform為止。 如果在此實作移轉階段需要結構描述，您將被強制使用以Adobe Analytics欄位為基礎的結構描述。 Adobe Experience Platform服務(例如Customer Journey Analytics)沒有prop或eVar的概念。 如果您的組織想要在未來使用自己的結構描述，以Analytics為主的結構描述可能會造成困難。</li><li>在對Web SDK進行實作變更後，您的組織就能更妥善地從Adobe Analytics移轉至Customer Journey Analytics。 如果您使用Web SDK傳送資料至Adobe Analytics，便不需要進行額外的實作變更即可將資料傳送至Adobe Experience Platform。 您可以改用資料準備將資料物件欄位對應到您的XDM結構描述。</li></ul>另請參閱 [從Adobe Analytics標籤擴充功能移轉至Web SDK標籤擴充功能](/help/implement/aep-edge/web-sdk/analytics-extension-to-web-sdk.md) 和 [從AppMeasurement移轉至Web SDK](../implement/aep-edge/web-sdk/appmeasurement-to-web-sdk.md) 以取得詳細資訊。 |  | 2024 年 4 月 |
| **僅限專案的許可權增強功能 [!UICONTROL 工作區] 元件** | 先前，如果使用者（使用者A）與另一個使用者（使用者B）共用專案，並授予使用者B專案的編輯許可權，則使用者B將能夠編輯專案。 但是，使用者B無法編輯 [!UICONTROL 快速區段] 內嵌在專案中。 該限制現已移除 — 使用者B可以編輯 [!UICONTROL 快速區段] 和嵌入共用專案的其他僅限專案元件。 |  | 2024 年 4 月 17 日 |
| **對使用相同的雲端帳戶 [!UICONTROL 資料摘要]， [!UICONTROL Data Warehouse]、和 [!UICONTROL 分類設定]** | 您建立的雲端帳戶和位置現在可用於匯出資料(具有 [!UICONTROL 資料摘要] 和 [!UICONTROL Data Warehouse])和匯入資料(使用 [!UICONTROL 分類設定])。<p> **設定帳戶時的變更：** 使用者可以 [設定雲端匯入和匯出帳戶](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) 和 [設定雲端匯入和匯出位置](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations) 其用途如下：<ul><li>使用匯入資料 [!UICONTROL 分類設定]</li><li>匯出資料，使用 [!UICONTROL 資料摘要]</li><li>匯出資料，使用 [!UICONTROL Data Warehouse].</li></ul><p>**從管理帳戶和位置時的變更 [!UICONTROL 位置] 頁面**：使用者可使用 [位置](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) 頁面（在下） [!UICONTROL 元件] > Loc動作)以檢視及管理其建立的所有帳戶與位置，無論其建立於何處。 <p>先前， [!UICONTROL 位置] 頁面僅套用至使用建立以匯入資料的帳戶 [!UICONTROL 分類設定].</p>**從管理位置時變更 [!UICONTROL Data Warehouse] 或 [!UICONTROL 分類設定]**<p>在指定的應用程式區域內管理位置時([!UICONTROL Data Warehouse] 或 [!UICONTROL 分類設定])，則只有在該特定應用程式區域中建立的位置才可使用。 例如，檢視 [!UICONTROL Data Warehouse] 僅應用程式區域 [!UICONTROL Data Warehouse] 位置可供使用。 無論帳戶建立於哪個應用程式區域，所有帳戶仍可在每個應用程式區域使用。 以前，無論帳戶和位置建立於哪個應用程式區域，都可在每個應用程式區域使用它們。 在檢視 [!UICONTROL 資料摘要] 應用程式區域。 | | 2024 年 4 月 17 日 |
| **管理員可以管理其組織中的所有位置和帳戶** | 「位置」標籤 (在「元件 > 位置」頁面上) 上的新選項可以讓管理員檢視和管理組織中的所有位置。<p>上的新選項 [位置](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) 帳號標籤（在「元件>位置」頁面上）可讓管理員檢視及管理組織中的所有帳號。</p> <p>以前，管理員只能檢視和管理他們建立的位置和帳戶。</p> |  | 2024 年 4 月 17 日 |
| **提高預設低流臨界值** | 在 **2024 年 4 月中旬**，Adobe 將開始提高預設報告套裝低流量臨界值，如下所示： ![低流量臨界值](assets/thresholds.png) 這只會影響目前設定低於新臨界值的變數。這些改變將逐步進行，我們預計這項工作將在&#x200B;**五月底**&#x200B;結束。隨著這些增加的推出，您可能會注意到高基數變數的變化：<ul><li>更多維度值可用於報告。</li><li>區段和計算量度可能包含更多資料。</li><li>以區段為主的虛擬報告套裝可能包含更多資料。</li><li>分類匯出可能包含更多資料。</li></ul> | 2024 年 4 月中旬 | 2024年5月31日 |
| **Activity Map 使用更少的 Web SDK 伺服器呼叫** | 目前，Activity Map 連結事件被視為是其本身事件並會產生額外費用。 <p>此增強功能會產生一些連結事件，並將這些事件封裝至下一個點擊中，類似於 AppMeasurement 處理事件的方式。</p> |  | 2024年5月31日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正下列分類問題：AN-343439、AN-343503、AN-343504、AN-343986、AN-344262、AN-344564、AN-345204、AN-345234
* 修正下列分類規則產生器問題：AN-341488、AN-342501、AN-345751
* 修正下列智慧型警報的問題： AN-343466；
* 修正以下分段問題：AN-342313
* 已修正下列Data Warehouse問題： AN-344292
* 已修正下列資料摘要問題： AN-339545、AN-340092、AN-342124、AN-342862、AN-343737、AN-344035、AN-344329、AN-344703、AN-344721、AN-344940、AN-345180、AN-345196、AN-345225、AN-345236、AN-345326、AN-345631、AN-345659
* 已修正下列資料來源問題： AN-343541
* 修正下列Analysis Workspace問題：AN-336303、AN-336472、AN-338422、AN-338556、AN-339718、AN-340147、AN-340301、AN-340421、AN-340951、AN-341172、AN-342905、AN-342909、AN-343448、AN-343570、AN-344050、AN-344182、AN-344763、AN-344768；
* 修正下列Analytics管理問題：AN-342519、AN-342523、AN-343623、AN-343882、AN-344237、AN-344829、AN-345235；
* 已修正下列A4T問題：AN-341619；AN-344402
* 已修正下列行動應用程式問題： AN-342010

### Analytics 其他修正

AN-336099、AN-337474、AN-337993、AN-339718、AN-339901、AN-340014、AN-341356、AN-343021、AN-343102、AN-343353、AN-343416、AN-340014、AN-344037、AN-344525、AN-345737

## 給 Adobe Analytics 管理員的重要通知 {#admin}

| 通知 | 新增或更新日期 | 說明 |
| ----------- | ---------- | ---------- |
| **13 個月的儲存有效期`cust_visids`** | 2024 年 3 月 20 日 | 即將發行的 Analytics Hit 處理引擎 (預計於 4 月或 5 月發行) 將開始強制執行 13 個月的 `cust_visids` 儲存有效期。如果報告套裝已啟用「啟用訪客聯繫」，則此設定用於尋找 `cust_visid` 是否有點擊時無 `cust_visid` 的 `visid_high/visid_low value`。目前，`visid_high/visid_low` 的 `cust_visid` 對應不會過期。在此版本中，如果自點擊時 `visid_high/visid_low` 有 `cust_visid` 以來已過去 13 個月或更長時間，對應將過期。 |
| **Adobe API 物件會員新增** | 2024 年 1 月 17 日 | Adobe 可能會為現有 API 物件隨時新增選擇性請求和回應會員 (名稱/值對)，恕不另行通知或變更版本設定。Adobe 建議您參考與我們的 API 整合的任何協力廠商工具的 API 文件，以便在不理解的情況下在處理過程中忽略此類新增。如果實施得當，此類新增對於您的實施來說是非破壞性的變更。Adobe 不會在未事先透過發行說明提供標準通知下刪除參數或新增所需參數。 |

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

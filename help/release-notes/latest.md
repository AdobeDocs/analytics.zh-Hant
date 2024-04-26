---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7468463e2fe1de16221b4528919b6abd6c8aedcb
workflow-type: ht
source-wordcount: '1445'
ht-degree: 100%

---

# Adobe Analytics 目前的發行說明 (2024 年 4 月)

**上次更新日期**：2024 年 4 月 17 日

這些發行說明涵蓋 2024 年 4 月 17 日至 2024 年 5 月的發行期間。Adobe Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以更可縮放、分階段的方法進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **串流媒體：將 Roku 資料傳送至 Adobe Experience Platform Edge Network** | 現在，[透過 Experience Platform Edge 安裝 Media Analytics](https://experienceleague.adobe.com/zh-hant/zh-hant/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) 時，您可以使用 Adobe Experience Platform Roku SDK 將串流媒體資料傳送至 Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **改進 Web SDK 移轉的工作流程** | 資料流現在會自動將 Web SDK 資料物件中的欄位直接對應到 Adob&#x200B;&#x200B;e Analytics。[資料物件對應](/help/implement/aep-edge/data-var-mapping.md)類似於 [XDM 物件對應](/help/implement/aep-edge/xdm-var-mapping.md)，但不需要 XDM 結構描述。這個改善的工作流程提供以下優點：<ul><li>此對應會延遲使用結構描述的要求，直到您準備好將資料傳送到 Adob&#x200B;&#x200B;e Experience Platform。如果在這個實施移轉的階段中需要架構，您將被迫使用以 Adob&#x200B;&#x200B;e Analytics 欄位為主的結構描述。Adobe Experience Platform 服務 (例如 Customer Journey Analytics) 沒有 props 或 eVar 的概念。如果您的組織希望將來使用自己的結構描述，則著重分析的結構描述可能會帶來困難。</li><li>在進行對 Web SDK 的實施變更後，您的組織就能更順利地從 Adobe Analytics 移轉到 Customer Journey Analytics。如果您使用 Web SDK 將資料傳送至 Adob&#x200B;&#x200B;e Analytics，則無需進行其他實施變更即可將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform。相反，您可以使用資料準備功能，將資料物件欄位對應到 XDM 結構描述。</li></ul>請參閱「[從 Adobe Analytics 標記擴充功能移轉至 Web SDK 標記擴充功能](/help/implement/aep-edge/web-sdk/analytics-extension-to-web-sdk.md)」和「[從 AppMeasurement 移轉到 Web SDK](../implement/aep-edge/web-sdk/appmeasurement-to-web-sdk.md)」，可了解更多。 |  | 2024 年 4 月 |
| **僅限專案 [!UICONTROL Workspace] 元件的權限增強** | 在過去，如果使用者 (使用者 A) 與另一個使用者 (使用者 B) 共用專案，並授予使用者 B 對專案的編輯權限，則使用者 B 將可編輯該專案。但是，使用者 B 無法編輯專案中嵌入的[!UICONTROL 快速區段]。這項限制現已移除：使用者 B 可以編輯[!UICONTROL 快速區段]，以及共用專案中嵌入的其他僅限專案的元件。 |  | 2024 年 4 月 17 日 |
| **針對[!UICONTROL 資料摘要]、[!UICONTROL Data Warehouse] 和[!UICONTROL 分類集]**&#x200B;使用相同的雲端帳戶 | 您建立的雲端帳戶和位置現在可用來匯出資料 (使用[!UICONTROL 資料摘要]和 [!UICONTROL Data Warehouse]) 並匯入資料 (使用[!UICONTROL 分類集])。<p> **設定帳戶時的變更：**&#x200B;使用者可以[設定雲端匯入和匯出帳戶](https://experienceleague.adobe.com/zh-hant/zh-hant/docs/analytics/components/locations/configure-import-accounts)以及[設定雲端匯入和匯出位置](https://experienceleague.adobe.com/zh-hant/zh-hant/docs/analytics/components/locations/configure-import-locations)，用於以下任一目的：<ul><li>使用[!UICONTROL 分類集]匯入資料</li><li>使用[!UICONTROL 資料摘要]匯出資料</li><li>使用 [!UICONTROL Data Warehouse] 匯出資料。</li></ul><p>**從「[!UICONTROL 位置]」頁面管理帳戶和位置時的變更**：使用者可以使用「[位置](https://experienceleague.adobe.com/zh-hant/zh-hant/docs/analytics/components/locations/locations-manager)」頁面 (在「[!UICONTROL 元件] > 位置」下) 來查看和管理他們建立的所有帳戶和位置，無論這些是在何處建立。 <p>在過去，「[!UICONTROL 位置]」頁面僅適用於為使用[!UICONTROL 分類集]匯入資料而建立的帳戶。</p>**從 [!UICONTROL Data Warehouse] 或「[!UICONTROL 分類集]**」管理位置時的變更<p>當管理特定應用區域 ([!UICONTROL Data Warehouse] 或[!UICONTROL 分類集]) 內的位置時，只有在該特定應用區域內建立的位置可使用。例如，當查看 [!UICONTROL Data Warehouse] 應用區域時，只有 [!UICONTROL Data Warehouse] 位置可使用。在每個應用區域中，所有帳戶仍然可使用，無論這些帳戶是在哪個應用區域中建立。以前，無論是在哪個應用區域建立，所有帳戶和位置在每個應用區域中都可使用。查看[!UICONTROL 資料摘要]應用區域時仍然是如此。 | | 2024 年 4 月 17 日 |
| **管理員可以管理其組織中的所有位置和帳戶** | 「位置」標籤 (在「元件 > 位置」頁面上) 上的新選項可以讓管理員檢視和管理組織中的所有位置。<p>「[位置](https://experienceleague.adobe.com/zh-hant/zh-hant/docs/analytics/components/locations/locations-manager)」帳戶標籤 (在「元件 > 位置」頁面上) 上的新選項可以讓管理員檢視和管理組織中的所有帳戶。</p> <p>在過去，管理員只能檢視和管理他們建立的位置和帳戶。</p> |  | 2024 年 4 月 17 日 |
| **提高預設低流臨界值** | 在 **2024 年 4 月中旬**，Adobe 將開始提高預設報告套裝低流量臨界值，如下所示： ![低流量臨界值](assets/thresholds.png) 這只會影響目前設定低於新臨界值的變數。這些改變將逐步進行，我們預計這項工作將在&#x200B;**五月底**&#x200B;結束。隨著這些增加的推出，您可能會注意到高基數變數的變化：<ul><li>更多維度值可用於報告。</li><li>區段和計算量度可能包含更多資料。</li><li>以區段為主的虛擬報告套裝可能包含更多資料。</li><li>分類匯出可能包含更多資料。</li></ul> | 2024 年 4 月中旬 | 2024 年 5 月 31 日 |
| **Activity Map 使用更少的 Web SDK 伺服器呼叫** | 目前，Activity Map 連結事件被視為是其本身事件並會產生額外費用。 <p>此增強功能會產生一些連結事件，並將這些事件封裝至下一個點擊中，類似於 AppMeasurement 處理事件的方式。</p> |  | 2024 年 5 月 31 日 |

{style="table-layout:auto"}

## Adobe Analytics 中的修正

* 修正以下分類問題：AN-343439；AN-343503；AN-343504；AN-343986；AN-344262；AN-344564；AN-345204；AN-345234
* 修正以下分類規則產生器問題：AN-341488；AN-342501；AN-345751
* 修正以下智慧型警報問題：AN-343466
* 修正以下分段問題：AN-342313
* 修正以下 Data Warehouse 問題：AN-344292
* 修正以下資料摘要問題：AN-339545；AN-340092；AN-342124；AN-342862；AN-343737；AN-344035；AN-344329；AN-344703；AN-344721；AN-344940；AN-345180；AN-345196；AN-345225；AN-345236；AN-345326；AN-345631；AN-345659
* 修正以下資料來源問題：AN-343541
* 修正以下 Analysis Workspace 問題：AN-336303；AN-336472；AN-338422；AN-338556；AN-339718；AN-340147；AN-340301；AN-340421；AN-340951；AN-341172；AN-342905；AN-342909；AN-343448；AN-343570；AN-344050；AN-344182；AN-344763；AN-344768；
* 修正以下 Analytics 管理員問題：AN-342519；AN-342523；AN-343623；AN-343882；AN-344237；AN-344829；AN-345235；
* 修正以下 A4T 問題：AN-341619；AN-344402
* 修正以下行動應用程式問題：AN-342010

### Analytics 其他修正

AN-336099；AN-337474；AN-337993；AN-339718；AN-339901；AN-340014；AN-341356；AN-343021；AN-343102；AN-343353；AN-343416；AN-340014；AN-344037；AN-344525；AN-345737

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

如需 AppMeasurement 版本 (版本 2.26.0) 最新的更新，請參閱 [AppMeasurement for JavaScript 發行說明](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/appmeasurement-updates.html?lang=zh-Hant)。


## 相關資源

* [2023 年舊版發行說明](/help/release-notes/2023.md)
* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/releases/latest.html?lang=zh-Hant)
* [Media Analytics 發行說明](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新版更新。

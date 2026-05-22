---
description: 探索您可以使用Advertising Analytics執行的所有功能，包括所需的許可權以及可用的維度和量度。
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
TQID: https://experienceleague.adobe.com/BY9Zpnhu8FzGDHePD-MuWtyMWOuJKRgC-wTr42-rlyU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: a9364d69-0c51-44bf-8b5f-6d99c04493b8id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 1132
ht-degree: 16%

---

# Advertising Analytics

Advertising Analytics可讓您在Adobe Analytics中以並排方式檢視所有Google Ads和Microsoft Advertising付費搜尋資料。 之前，您必須在Google或每個廣告介面中檢視任何Adobe Advertising Ads或Microsoft Advertising資料。 您現在可以直接從搜尋引擎以及AMO ID例項（按一下例項）取得曝光數、點選數和成本資料。

將來自這些搜尋引擎的資料放在Adobe Analytics中，您就能運用Analysis Workspace的強大功能分析相同資料。 Workspace中新的[付費搜尋效能](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md)範本有助於進行此分析。

![](assets/aa_aw.png)

以下是這次整合所針對的客群：

* 需要為付費搜尋行銷人員收集效能報告的&#x200B;**分析師**。
* 想要了解向自己網站傳送多少流量以及客戶轉換率的&#x200B;**付費搜尋行銷人員**。 我有哪些符合成本效益的廣告促銷活動？


## 先決條件 {#prerequisites}

* Advertising Analytics僅適用於Adobe Analytics [Select](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html)、[Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/prime.html)和[Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/ultimate.html) SKU。
* 此功能適用於未使用Adobe Advertising的客戶。
* 您必須是Adobe Analytics管理員才能存取Advertising Analytics，或屬於已[授與Advertising Analytics存取權](/help/integrate/c-advertising-analytics/overview.md#permissions)的產品設定檔。
* 針對您要檢視Google Ads或Microsoft Advertising搜尋資料的任何報表套裝，您必須[啟用Advertising Analytics報表套裝](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) （ **[!UICONTROL 管理員]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL Advertising Analytics設定]**）。
* 您需要對您要與Adobe Analytics整合的搜尋帳戶具有編輯許可權的使用者的登入認證，例如Google帳戶ID和密碼。
* 若是Microsoft Advertising，您也需要[[!UICONTROL 帳戶ID]和[!UICONTROL 經理帳戶ID]](c-adanalytics-workflow/aa-locate-account-id.md)。

## Advertising Analytics 權限 {#permissions}

Analytics有兩個許可權會自動授與Analytics管理員。 然後，管理員可以選擇將這些許可權授予非管理員。

| 權限 | 定義 | 如果您已登入Adobe CX Enterprise，請授與許可權 |
| --- | --- | --- |
| Advertising Analytics 管理 | 可讓使用者設定/編輯/檢視Advertising搜尋帳戶。 | 登入[adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL 產品] > [!UICONTROL Adobe Analytics] > [!UICONTROL 產品設定檔] > [!UICONTROL 許可權]索引標籤> [!UICONTROL Analytics工具] > [!UICONTROL Advertising Analytics管理] |
| Advertising Analytics 設定 | 可讓使用者設定要為 Advertising Analytics 佈建的報告套裝。 | 登入[adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL 產品] > [!UICONTROL Adobe Analytics] > [!UICONTROL 產品設定檔] > [!UICONTROL 許可權]索引標籤> [!UICONTROL Analytics工具] > [!UICONTROL Advertising Analytics設定] |

## Advertising Analytics維度和量度 {#dimensions-metrics}

Advertising Analytics將下列維度和量度新增至Analysis Workspace、Report Builder及Analytics Reporting API。

### 維度

>[!IMPORTANT]
>
>這次整合會透過 AMO ID 變數的分類，建立一組新的維度。 這些新維度不會影響或修改您現有的行銷管道或行銷活動追蹤變數維度。 當訪客從付費搜尋廣告登入網站時，AMO ID會連線至訪客的設定檔。 因此，AMO維度可用來劃分此整合提供的AMO量度，以及訪客在下游擷取的任何資料（造訪次數、訪客、頁面檢視次數、跳出率、訂購、收入、自訂事件等）。 在報告其他站上量度時，這些量度也可依其他維度劃分。
>
>這些量度的分類每天都會更新。 因此，如果您變更搜尋引擎中的中繼資料，您可能要等到第二天更新分類後，才會看到這些變更反映。

| 分類（維度）名稱 | 定義 |
| --- | --- |
| **[!UICONTROL 關鍵字MatchType (AMO ID)]** | 關鍵字元合型別。 值通常會是廣泛、確切的詞句；如果沒有符合類型的廣告類型，則沒有值。 |
| **[!UICONTROL 廣告平台(AMO ID)]** | 搜尋引擎名稱。 值可以包括「Google AdWords」或「Microsoft Bing Ads」。 |
| **[!UICONTROL 帳戶(AMO ID)]** | 被追蹤的搜尋引擎帳戶名稱。 |
| **[!UICONTROL 行銷活動(AMO ID)]** | 搜尋引擎帳戶中的行銷活動名稱。 |
| **[!UICONTROL 廣告群組(AMO ID)]** | 搜尋引擎促銷活動中的廣告群組名稱。 |
| **[!UICONTROL 廣告(AMO ID)]** | 廣告上使用的廣告標題+廣告說明。 |
| **[!UICONTROL 關鍵字(AMO ID)]** | 來自您搜尋引擎帳戶的「關鍵字」值。 |
| **[!UICONTROL 符合型別(AMO ID)]** | 關鍵字元合指派給您的關鍵字的型別。 值通常會是廣泛、確切的詞句；如果沒有符合類型的廣告類型，則沒有值。 |
| **[!UICONTROL 廣告型別(AMO ID)]** | 投放的廣告類型，通常為「文字廣告」。 |
| **[!UICONTROL 廣告標題(AMO ID)]** | 您的廣告中使用的標題物件。 |
| **[!UICONTROL 廣告說明(AMO ID)]** | 廣告中使用的廣告說明物件。 |
| **[!UICONTROL 廣告顯示URL (AMO ID)]** | 廣告中使用的廣告顯示URL物件。 |
| **[!UICONTROL 廣告目的地URL (AMO ID)]** | 指派給您廣告的登陸頁面URL或最終URL。 |
| **[!UICONTROL 網路(AMO ID)]** | 提供廣告的網路。 若為 Advertising Analytics，此值一律為「Search」。 |
| **[!UICONTROL 位置(AMO ID)]** | 受管理的位置網站（適用於內容網路）。 只有Managed版位會使用此維度。 |
| **[!UICONTROL 產品目標(AMO ID)]** | 用於PLA廣告的產品目標名稱（不是實際購買的產品）。 |
| **[!UICONTROL 最佳化(AMO ID)]** | Advertising Analytics未使用。 僅限Adobe Advertising客戶使用。 |
| **[!UICONTROL 裝置(AMO ID)]** | 今天未使用。 針對指定的廣告目標裝置型別（例如行動裝置、案頭） （而非訪客的實際裝置）提供潛在未來產品增強功能的預留位置。 |

### 量度

>[!IMPORTANT]
>
>Advertising Analytics 提供的量度 (如下所示) 屬於搜尋引擎的摘要層級資料。 未連線至Analytics訪客設定檔。 它們只會連線至AMO ID變數及其關聯的分類維度。 因此，不應根據AMO ID維度以外的任何維度/區段來報告這些量度/區段。 這麼做會導致Analytics顯示資料的零。 您可以將它們與其他量度一起納入計算量度中，但這些計算量度也只應依AMO ID維度劃分。
>
>這些量度是每日取得的資料，因此不會有當天的資料。 也不應該在低於每日的詳細程度上報告這些事件。
>
>登陸頁面上設定AMO ID時，會設定AMO ID例項量度（即點進）。 此量度會在登陸頁面點選時即時擷取，並可搭配其他也在登陸頁面上設定的維度用於劃分。

| 量度名稱 | 定義 |
| --- | --- |
| **[!UICONTROL AMO曝光數]** | 搜尋引擎所報告的廣告曝光次數。 |
| **[!UICONTROL AMO點按]** | 搜尋引擎報告的廣告點選次數。 |
| **[!UICONTROL AMO成本]** | 搜尋引擎所報告的每個關鍵字/廣告的已付成本。 |

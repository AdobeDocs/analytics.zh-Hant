---
description: 探索您可以使用Advertising Analytics執行的所有功能，包括所需的許可權以及可用的維度和量度。
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 15%

---

# Advertising Analytics

Advertising Analytics可讓您在Adobe Analytics中以並排方式檢視所有Google Ads和Microsoft Advertising付費搜尋資料。 之前，您必須在Google或每個廣告介面中檢視任何Adobe Advertising Ads或Microsoft Advertising資料。 您現在可以直接從搜尋引擎以及AMO ID例項（按一下例項）取得曝光數、點選數和成本資料。

By bringing the data from these search engines together in Adobe Analytics, you can analyze that same data by using the power of Analysis Workspace. A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

以下是這次整合所針對的客群：

* The **Analyst** who needs to collect performance reports for the Paid Search Marketer.
* 想要了解向自己網站傳送多少流量以及客戶轉換率的&#x200B;**付費搜尋行銷人員**。我有哪些符合成本效益的廣告促銷活動？


## 先決條件 {#prerequisites}

* Advertising Analytics僅適用於Adobe Analytics [Select](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html)、[Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/prime.html)和[Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/ultimate.html) SKU。
* 此功能適用於未使用Adobe Advertising的客戶。
* 您必須是Adobe Analytics管理員才能存取Advertising Analytics，或屬於已[授與Advertising Analytics存取權](/help/integrate/c-advertising-analytics/overview.md#permissions)的產品設定檔。
* For any report suite where you want to view Google Ads or Microsoft Advertising search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).
* You need login credentials for a user with edit permissions to the search account/s which you want to integrate with Adobe Analytics, such as a Google Account ID and password.
* 若是Microsoft Advertising，您也需要[[!UICONTROL 帳戶ID]和[!UICONTROL 經理帳戶ID]](c-adanalytics-workflow/aa-locate-account-id.md)。

## Advertising Analytics 權限 {#permissions}

Analytics有兩個許可權會自動授與Analytics管理員。 然後，管理員可以選擇將這些許可權授予非管理員。

| 權限 | 定義 | 如果您已登入Adobe Experience Cloud，請授與許可權 |
| --- | --- | --- |
| Advertising Analytics 管理 | 可讓使用者設定/編輯/檢視Advertising搜尋帳戶。 | 登入[adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL 產品] > [!UICONTROL Adobe Analytics] > [!UICONTROL 產品設定檔] > [!UICONTROL 許可權]索引標籤> [!UICONTROL Analytics工具] > [!UICONTROL Advertising Analytics管理] |
| Advertising Analytics 設定 | 可讓使用者設定要為 Advertising Analytics 佈建的報告套裝。 | Log in to [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] tab > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Configuration] |

## Advertising Analytics dimensions and metrics {#dimensions-metrics}

Advertising Analytics adds the following dimensions and metrics to Analysis Workspace, Report Builder, and the Analytics Reporting API.

### 維度

>[!IMPORTANT]
>
>這次整合會透過 AMO ID 變數的分類，建立一組新的維度。這些新維度不會影響或修改您現有的行銷管道或行銷活動追蹤變數維度。 當訪客從付費搜尋廣告登入網站時，AMO ID會連線至訪客的設定檔。 因此，AMO維度可用來劃分此整合提供的AMO量度，以及訪客在下游擷取的任何資料（造訪次數、訪客、頁面檢視次數、跳出率、訂購、收入、自訂事件等）。 在報告其他站上量度時，這些量度也可依其他維度劃分。
>
>The classifications for these metrics are updated daily. As such, if you make changes to the meta data in a search engine, you may not see those changes reflect until the following day when the classifications are updated.

| Classification (dimension) name | 定義 |
| --- | --- |
| **[!UICONTROL 關鍵字MatchType (AMO ID)]** | 關鍵字元合型別。 值通常會是廣泛、確切的詞句；如果沒有符合類型的廣告類型，則沒有值。 |
| **[!UICONTROL 廣告平台(AMO ID)]** | 搜尋引擎名稱。 值可以包括「Google AdWords」或「Microsoft Bing Ads」。 |
| **[!UICONTROL 帳戶(AMO ID)]** | The name of the search engine account that is being tracked. |
| **[!UICONTROL Campaign (AMO ID)]** | The name of the campaign in your search engine account. |
| **[!UICONTROL Ad Group (AMO ID)]** | The name of the ad group in your search engine campaigns. |
| **[!UICONTROL 廣告(AMO ID)]** | 廣告上使用的廣告標題+廣告說明。 |
| **[!UICONTROL 關鍵字(AMO ID)]** | 來自您搜尋引擎帳戶的「關鍵字」值。 |
| **[!UICONTROL 符合型別(AMO ID)]** | The Keyword Match Type assigned to your keyword. 值通常會是廣泛、確切的詞句；如果沒有符合類型的廣告類型，則沒有值。 |
| **[!UICONTROL 廣告型別(AMO ID)]** | 投放的廣告類型，通常為「文字廣告」。 |
| **[!UICONTROL 廣告標題(AMO ID)]** | 您的廣告中使用的標題物件。 |
| **[!UICONTROL 廣告說明(AMO ID)]** | 廣告中使用的廣告說明物件。 |
| **[!UICONTROL 廣告顯示URL (AMO ID)]** | 廣告中使用的廣告顯示URL物件。 |
| **[!UICONTROL 廣告目的地URL (AMO ID)]** | 指派給您廣告的登陸頁面URL或最終URL。 |
| **[!UICONTROL Network (AMO ID)]** | The network the Ad is being served on. 若為 Advertising Analytics，此值一律為「Search」。 |
| **[!UICONTROL Placement (AMO ID)]** | 受管理的位置網站（適用於內容網路）。 只有Managed版位會使用此維度。 |
| **[!UICONTROL 產品目標(AMO ID)]** | 用於PLA廣告的產品目標名稱（不是實際購買的產品）。 |
| **[!UICONTROL 最佳化(AMO ID)]** | Advertising Analytics未使用。 It is used only by Adobe Advertising customers. |
| **[!UICONTROL Device (AMO ID)]** | Not used today. 針對指定的廣告目標裝置型別（例如行動裝置、案頭） （而非訪客的實際裝置）提供潛在未來產品增強功能的預留位置。 |

### 量度

>[!IMPORTANT]
>
>Advertising Analytics 提供的量度 (如下所示) 屬於搜尋引擎的摘要層級資料。未連線至Analytics訪客設定檔。 它們只會連線至AMO ID變數及其關聯的分類維度。 因此，不應根據AMO ID維度以外的任何維度/區段來報告這些量度/區段。 這麼做會導致Analytics顯示資料的零。 您可以將它們與其他量度一起納入計算量度中，但這些計算量度也只應依AMO ID維度劃分。
>
>這些量度是每日取得的資料，因此不會有當天的資料。 也不應該在低於每日的詳細程度上報告這些事件。
>
>登陸頁面上設定AMO ID時，會設定AMO ID例項量度（即點進）。 此量度會在登陸頁面點選時即時擷取，並可搭配其他也在登陸頁面上設定的維度用於劃分。

| 量度名稱 | 定義 |
| --- | --- |
| **[!UICONTROL AMO曝光數]** | The number of ad impressions as reported by the search engine. |
| **[!UICONTROL AMO Clicks]** | 搜尋引擎報告的廣告點選次數。 |
| **[!UICONTROL AMO成本]** | 搜尋引擎所報告的每個關鍵字/廣告的已付成本。 |

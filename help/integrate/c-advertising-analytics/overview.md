---
description: 在此詳細指南中探索您可以使用 Advertising Analytics 進行的所有功能，包括所需的權限以及可用的維度和量度。
title: Advertising Analytics 指南
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
translation-type: tm+mt
source-git-commit: 797dd2c700cd6e11db91e3b5e6bf4b7bfbefdabe
workflow-type: tm+mt
source-wordcount: '1259'
ht-degree: 96%

---

# Advertising Analytics 指南

Advertising Analytics 可讓您在 Adobe Analytics 中以並排方式查看所有 Google 和 Bing 付費搜尋資料。以往，您只能在 Adobe Advertising Cloud (AMO) 或 Google/Bing 檢視 Google AdWords/DFA 或 Microsoft Bing Ads 資料。您現在將在Adobe Analytics內取得下列資料：直接從搜尋引擎以及AMO ID例項（按一下例項）中取得印象、點按、成本資料。 Google已於2019年9月取消這些量度的權限，因此將不再收集品質分數和平均位置。

>[!NOTE]
>
>Microsoft Bing 已於 2019 年 3 月 31 日併購 Yahoo Gemini，因此 Yahoo Gemini 廣告帳戶選項已無法繼續使用。

我們將來自這些搜尋引擎的資料全都帶到 Adobe Analytics 中，以便您運用 Analysis Workspace 的強大功能分析相同的資料。新的[工作區付費搜尋績效](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md)範本有助於進行此分析。

![](assets/aa_aw.png)

以下是這次整合鎖定的目標對象：

* 需要為付費搜尋行銷人員收集績效報告的&#x200B;**分析人員**。
* 想要了解向自己網站傳送多少流量以及客戶轉換率的&#x200B;**付費搜尋行銷人員**。我有哪些符合成本效益的廣告促銷活動？

## 必備條件 {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics 只適用於 Adobe Analytics [Select](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html)、[Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics/prime.html) 及 [Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics/ultimate.html) 的 SKU。

* 此功能適用於非 Advertising Cloud 以及非 AMO 的客戶。
* 您必須成為 Adobe Analytics 管理員才能存取 Advertising Analytics。隨後，您便可以將[存取權限授予](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369)非管理員使用者。
* 無論您要在任何 Analytics 報表套裝中檢視 Google/Bing 搜尋資料，該套裝報表都必須[對應至您的 Experience Cloud 組織](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/about-core-services/report-suite-mapping.html)。
* 針對您要檢視 Google/Bing 搜尋資料的任何報表套裝，請[啟用 Advertising Analytics 報表套裝](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) (**[!UICONTROL 「管理員]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL Advertising Analytics 設定」]**)。

* 若要將搜尋帳戶整合至 Adobe Analytics，您需要擁有具備編輯權限之帳戶的使用者登入憑證，例如 Google 帳戶 ID 和密碼。
* 若是 Bing 廣告，則需要使用 Bing 客戶 ID。
* 如果您使用 Internet Explorer 11 (或更早版本)，便無法成功為這三個搜尋引擎[設定廣告帳戶](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)。請改用其他網頁瀏覽器。

## Advertising Analytics 權限 {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics 會自動授予 Analytics 管理員兩項權限。之後，管理員便可以選擇將這些權限授予非管理員使用者。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 權限 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 在 Adobe Analytics 中授予權限 </th> 
   <th colname="col4" class="entry"> 在登入 Adobe Experience Cloud 的情況下授予權限 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 管理 </p> </td> 
   <td colname="col2"> <p>可讓使用者設定/編輯/檢視廣告搜尋帳戶。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">使用者管理 </span> &gt; <span class="uicontrol">群組</span> &gt; <span class="uicontrol">編輯所有報表存取權</span> &gt; <span class="uicontrol">自訂 Analytics 工具</span> &gt; <span class="uicontrol">Advertising Analytics 管理」</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol">登入 adminconsole.adobe.com</span> &gt; <span class="uicontrol">「產品</span> &gt; <span class="uicontrol">產品設定檔</span> &gt; <span class="uicontrol">權限標籤</span> &gt; <span class="uicontrol">Analytics 工具</span> &gt; <span class="uicontrol">Advertising Analytics 管理」</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 設定 </p> </td> 
   <td colname="col2"> <p>可讓使用者設定要為 Advertising Analytics 佈建的報表套裝。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">使用者管理 </span> &gt; <span class="uicontrol">群組</span> &gt; <span class="uicontrol">編輯所有報表存取權</span> &gt; <span class="uicontrol">自訂報表套裝工具</span> &gt; <span class="uicontrol">Advertising Analytics 設定」</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol">登入 adminconsole.adobe.com</span> &gt; <span class="uicontrol">「產品</span> &gt; <span class="uicontrol">產品設定檔</span> &gt; <span class="uicontrol">權限標籤</span> &gt; <span class="uicontrol">報表套裝工具</span> &gt; <span class="uicontrol">Advertising Analytics 設定」</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Analytics 維度和量度 {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analytics 將以下維度和量度新增至 Analysis Workspace、Reports &amp; Analytics、Report Builder 及 Analytics 報表 API。

**維度**

>[!IMPORTANT]
>
>這次整合會透過 AMO ID 變數的分類，建立一組新的維度。這些新建立的維度並不會影響或修改您現有的行銷管道或宣傳活動追蹤變數維度。當訪客從付費搜尋廣告登陸網站時，AMO ID 便會連結到訪客的個人資料。在這種情況下，AMO 維度可用來劃分此整合提供的 AMO 量度以及訪客於下游擷取的任資料 (造訪次數、訪客數、頁面檢視次數、反彈率、訂單、收入、自訂事件等等)。在報告其他站上量度時，也可以透過其他維度劃分這些資料。
>
>這些量度的分類會每天更新。因此，如果您在搜尋引擎內變更中繼資料，您可能要在分類更新後翌日才能看到這些變更內容。

| 分類 (維度) 名稱 | 定義 |
|--- |--- |
| 關鍵字比對類型 (AMO ID) | 關鍵字比對類型。值通常會是廣泛、確切的詞句；如果沒有符合類型的廣告類型，則沒有值。 |
| 廣告平台 (AMO ID) | 搜尋引擎名稱。值可以包括 Google AdWords 或 Microsoft Bing Ads。 |
| 帳戶 (AMO ID) | 受追蹤搜尋引擎帳戶的名稱。 |
| 宣傳活動 (AMO ID) | 在搜尋引擎帳戶中的宣傳活動名稱。 |
| 廣告群組 (AMO ID) | 在搜尋引擎中的廣告群組名稱。 |
| 廣告 (AMO ID) | 用於廣告的廣告標題與廣告說明。 |
| 關鍵字 (AMO ID) | 搜尋引擎帳戶的關鍵字值 |
| 比對類型 (AMO ID) | 指派給關鍵字的關鍵字比對類型。值通常會是廣泛、確切的詞句；如果沒有符合類型的廣告類型，則沒有值。 |
| 廣告類型 (AMO ID) | 投放的廣告類型，通常為「文字廣告」。 |
| 廣告標題 (AMO ID) | 廣告中使用的標題物件。 |
| 廣告說明 (AMO ID) | 廣告中使用的廣告說明物件。 |
| 廣告顯示 URL (AMO ID) | 廣告中使用的廣告顯示 URL 物件。 |
| 廣告目的地 URL (AMO ID) | 指派給廣告的登陸頁面 URL 或最終 URL。 |
| 網路 (AMO ID) | 正在投放廣告的網路。若為 Advertising Analytics，此值一律為「Search」。 |
| 版位 (AMO ID) | 託管式版位網站 (內容網路用)。僅託管式版位會使用此維度。 |
| 產品目標 (AMO ID) | 用於 PLA 廣告的產品目標名稱 (非購買的實際產品)。 |
| 最佳化 (AMO ID) | Advertising Analytics 不使用。僅 Advertising Cloud 客戶會使用。 |
| 裝置 (AMO ID) | 目前不使用。廣告指定目標裝置 (而非訪客實際使用的裝置) 類型 (例如行動裝置或桌上型電腦)，未來可能的產品增強功能預留位置。 |

**量度**

>[!IMPORTANT]
>
>Advertising Analytics 提供的量度 (如下所示) 屬於搜尋引擎的摘要層級資料。這些量度並未連結到 Analytics 訪客個人資料，而是只連結到 AMO ID 變數及其相關聯的分類維度。在這種情況下，除了依據 AMO ID 維度的量度外，這些量度都不應由任何維度/區段進行報告。這樣做會導致 Analytics 將資料顯示為零。您可以將其與其他量度一併加入計算量度中，但這些計算量度僅應由 AMO ID 維度劃分。
>
>這些量度採用的是每日所得的資料，因此不會有當日的資料。此外，這些量度的報告精細度也不應少於每日報告一次。
>
>若登陸頁面設定了 AMO ID，則會設定一個 AMO ID 實例量度 (即「點閱率」)。此量度會以登陸頁面的點擊即時進行擷取，並可以由該登陸頁面設定的其他維度劃分。

| 量度名稱 | 定義 |
|--- |--- |
| AMO 曝光數 | 根據搜尋引擎報告的廣告曝光次數。 |
| AMO 點選次數 | 根據搜尋引擎報告的廣告點選次數。 |
| AMO 成本 | 根據搜尋引擎報告，所獲悉之您為每個關鍵字/廣告支付的成本。 |

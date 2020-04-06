---
description: 'null'
title: Advertising Analytics 概觀
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Advertising Analytics 概觀

Advertising Analytics 可讓您在 Adobe Analytics 中以並排方式查看所有 Google 和 Bing 付費搜尋資料。以往，您只能在 Adobe Advertising Cloud (AMO) 或 Google/Bing 檢視 Google AdWords/DFA 或 Microsoft Bing Ads 資料。現在，您可以在 Adobe Analytics 中直接利用搜尋引擎及 AMO ID 實例 (按一下實例)，取得以下資料：曝光數、點選次數、成本、品質分數和平均位置。

>[!NOTE] Microsoft Bing 已於 2019 年 3 月 31 日併購 Yahoo Gemini，因此 Yahoo Gemini 廣告帳戶選項已無法繼續使用。

借由將這些搜尋引擎的資料匯整在Adobe Analytics中，您就可以運用分析工作區的強大功能來分析相同的資料。 A new [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) template in Workspace facilitates this analysis.

![](assets/aa_aw.png)

以下是這次整合鎖定的目標對象：

* 需要 **為付費搜尋行銷** 人員收集績效報表的分析師。
* 想要了解向自己網站傳送多少流量以及客戶轉換率的&#x200B;**付費搜尋行銷人員**。我有哪些符合成本效益的廣告促銷活動？

## 必備條件 {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics is available for Adobe Analytics [Select](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics/prime.html), and [Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics/ultimate.html) SKUs only.

* 此功能適用於非Advertising Cloud和非AMO客戶。
* 您必須是Adobe Analytics管理員才能存取Advertising Analytics。 之後，您可以 [將存取權限授](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) 予非管理員。
* 無論您要在任何 Analytics 報表套裝中檢視 Google/Bing 搜尋資料，該套裝報表都必須[對應至您的 Experience Cloud 組織](https://marketing.adobe.com/resources/help/zh_TW/mcloud/report-suite-mapping.html)。
* For any report suite where you want to view Google/Bing search data, you must [enable those report suite/s for Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* 您需要具有您要與Adobe Analytics整合之搜尋帳戶編輯權限（例如Google帳戶ID和密碼）的使用者的登入認證。
* 若是Bing Ads，您也需要Bing Customer ID。
* If you use Internet Explorer 11 (or earlier), you will not be able to successfully [set up an advertising account](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) for any of the three search engines. 請改用其他網頁瀏覽器。

## Advertising Analytics 權限 {#section_FCC58EB635954A32990D4E67B52B4369}

Analytics有兩個權限會自動授予Analytics管理員。 然後管理員可以選擇將這些權限授予非管理員。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 權限 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 在Adobe Analytics中授予權限 </th> 
   <th colname="col4" class="entry"> 如果您已登入Adobe Experience Cloud，請授予權限 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 管理 </p> </td> 
   <td colname="col2"> <p>可讓使用者設定／編輯／檢視廣告搜尋帳戶。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">使用者管理 </span> &gt; <span class="uicontrol">群組</span> &gt; <span class="uicontrol">編輯所有報表存取權</span> &gt; <span class="uicontrol">自訂 Analytics 工具</span> &gt; <span class="uicontrol">Advertising Analytics 管理」</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol">登入 adminconsole.adobe.com</span> &gt; <span class="uicontrol">「產品</span> &gt; <span class="uicontrol">產品設定檔</span> &gt; <span class="uicontrol">權限標籤</span> &gt; <span class="uicontrol">Analytics 工具</span> &gt; <span class="uicontrol">Advertising Analytics 管理」</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertising Analytics 設定 </p> </td> 
   <td colname="col2"> <p>可讓使用者設定要布建給Advertising Analytics的報表套裝。 </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">使用者管理 </span> &gt; <span class="uicontrol">群組</span> &gt; <span class="uicontrol">編輯所有報表存取權</span> &gt; <span class="uicontrol">自訂報表套裝工具</span> &gt; <span class="uicontrol">Advertising Analytics 設定」</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol">登入 adminconsole.adobe.com</span> &gt; <span class="uicontrol">「產品</span> &gt; <span class="uicontrol">產品設定檔</span> &gt; <span class="uicontrol">權限標籤</span> &gt; <span class="uicontrol">報表套裝工具</span> &gt; <span class="uicontrol">Advertising Analytics 設定」</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Analytics 維度和量度 {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analytics會將下列維度和量度新增至分析工作區、報告與分析、報告建立工具和Analytics報表API。

**維度**

>[!IMPORTANT]
>
>這次整合會透過 AMO ID 變數的分類，建立一組新的維度。這些新維度不會影響或修改您現有的行銷渠道或促銷活動追蹤變數維度。 當訪客從付費搜尋廣告登入網站時，AMO ID會連線至訪客的個人資料。 因此，AMO維度可用來劃分此整合所提供的AMO量度，以及訪客下游擷取的任何資料（瀏覽、訪客、頁面檢視、反彈率、訂購、收入、自訂事件等）。 在報告其他Onsite量度時，也可依其他維度加以劃分。
>
>這些量度的分類會每日更新。 因此，如果您在搜尋引擎中變更中繼資料，您可能會在下一天更新分類時，才看到這些變更所反映的內容。

| 分類（維度）名稱 | 定義 |
|--- |--- |
| 關鍵字元合類型(AMO ID) | 關鍵字元合類型。如果廣告類型沒有符合類型，則值通常會是廣泛、片語、完全或無值。 |
| 廣告平台(AMO ID) | 搜尋引擎名稱。 值可以包括 Google AdWords 或 Microsoft Bing Ads。 |
| 帳戶(AMO ID) | 正在追蹤的搜尋引擎帳戶名稱。 |
| 促銷活動(AMO ID) | 搜尋引擎帳戶中促銷活動的名稱。 |
| 廣告群組(AMO ID) | 搜尋引擎促銷活動中的廣告群組名稱。 |
| 廣告(AMO ID) | 用於廣告的廣告標題與廣告說明。 |
| 關鍵字(AMO ID) | 搜尋引擎帳戶的關鍵字值 |
| 符合類型(AMO ID) | 指派給關鍵字的關鍵字符合類型。值通常是「廣泛」、「確切」或「詞語」；如果沒有符合類型的廣告類型，則值為「無」。 |
| 廣告類型(AMO ID) | 投放的廣告類型，通常為「文字廣告」。 |
| 廣告標題(AMO ID) | 廣告中使用的標題物件. |
| 廣告說明(AMO ID) | 廣告中使用的廣告說明物件. |
| 廣告顯示URL(AMO ID) | 廣告中使用的廣告顯示 URL 物件. |
| 廣告目標URL(AMO ID) | 指派給廣告的登陸頁面 URL 或最終 URL. |
| 網路(AMO ID) | 廣告所服務的網路。 若為 Advertising Analytics，此值一律為「Search」。 |
| 位置(AMO ID) | 託管式刊登網站 (供內容網路使用)。僅有託管式刊登會使用此維度。 |
| 產品目標(AMO ID) | 用於 PLA 廣告的產品目標名稱 (非購買的實際產品). |
| 最佳化(AMO ID) | Advertising Analytics不會使用此功能。 它僅供Advertising Cloud客戶使用。 |
| 裝置(AMO ID) | 今天不用。預留位置，讓未來產品可能增強至廣告的指定目標裝置類型（例如行動裝置、案頭）（而非訪客的實際裝置）。 |

**量度**

>[!IMPORTANT]
>
>Advertising Analytics 提供的量度 (如下所示) 屬於搜尋引擎的摘要層級資料。它們未連結至Analytics訪客資料。 這些變數只會連線至AMO ID變數及其相關的分類維度。 因此，除基於AMO ID維度的維度外，任何維度／區段都不應報告這些維度／區段。 這麼做會導致Analytics為資料顯示零。 您可以將這些量度加入其他量度的計算量度中，但這些計算量度也應僅依AMO ID維度劃分。
>
>這些量度是每日來源的資料，因此不會包含當天的資料。 也不應以低於每日的粒度來報告。
>
>在登陸頁面上設定AMO ID時，會設定「AMO ID例項」量度（即點進）。 此量度會隨著著著陸頁面點擊即時擷取，並可用於劃分，其他維度也設定在著陸頁面上。

| 量度名稱 | 定義 |
|--- |--- |
| AMO 曝光數 | 由搜尋引擎報告的廣告印象數。 |
| AMO 點擊次數 | 搜尋引擎報告的廣告點按次數。 |
| AMO 成本 | 搜尋引擎所報告的每個關鍵字／廣告的付費成本。 |
| 平均 Pos | 反映由搜尋引擎報告之廣告平均位置的計算量度。 |
| 平均品質分數 | 反映搜尋引擎所報告之平均品質分數的計算量度。 |

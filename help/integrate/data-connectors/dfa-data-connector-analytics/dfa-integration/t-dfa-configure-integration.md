---
description: 逐步執行 DFA Data connectors 整合。
seo-description: 逐步執行 DFA Data connectors 整合。
seo-title: 設定 DFA 整合
title: 設定 DFA 整合
uuid: 4c2ac58a-87c6-46f3-9033-9404beb18c39
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 設定 DFA 整合{#configure-the-dfa-integration}

逐步執行 DFA Data connectors 整合。

設定頁面會提供整合的概述，以及實用的相關資訊連結。此整合會同時產生 Adobe 和 DoubleClick 的相關費用。請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。

1. [!DNL Adobe Analytics]登入。
1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Locate **[!UICONTROL DoubleClick DFA]**, then click **[!UICONTROL Add New]**.

   ![步驟結果](assets/wizard-01.png)

   On each page of the Integration Wizard, provide the required information, then click **[!UICONTROL Next]**. 下表說明您透過此精靈完成整合所需的資訊。

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 精靈頁面 # </th> 
   <th colname="col2" class="entry"> 欄位 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 整合名稱 </td> 
   <td colname="col3"> Genesis 在報表套裝的「作用中的整合清單」中顯示的整合名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> 整合電子郵件地址 </td> 
   <td colname="col3"> 接收此整合之所有相關通知的電子郵件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 使用者名稱 </td> 
   <td colname="col3"> 要用於此整合的 DFA API 使用者名稱。若要讓使用者可以進行 API 登入，請在 DFA 介面中勾選 API 屬性。啟用 API 登入後會出現密碼欄位，提供使用者的密碼。此密碼會連同使用者名稱輸入至精靈中，以進行驗證。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 密碼 </td> 
   <td colname="col3"> DFA API 密碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> 廣告主 ID </td> 
   <td colname="col3"> <p>DFA 廣告主 ID 或父項 Floodlight 設定 ID。Data connectors 會使用此 ID 來識別要追蹤的 DFA 廣告主 (1.5 版的整合)。整合2.0版未使用此廣告商ID-將會查閱並使用父Floodlight設定ID。請參閱畫面上的指示 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA 廣告變數 </td> 
   <td colname="col3"> 接收 DFA 促銷活動屬性、曝光數和點按資料的 Analytics eVar。這通常是追蹤代碼 eVar (<span class="varname"> s. campaign </span>)，但您可以選擇任何可用的eVar。Data connectors 也會將下列 DFA 相關分類新增至選取的 eVar: <p><b>促銷活動</b>: 一個提供給多個網站的廣告集合，可傳達一般訊息。 </p> <p><b>網站名稱</b>: 提供廣告的網站。 </p> <p><b>廣告名稱</b>: 廣告名稱，如您的 DFA 帳戶所定義。 </p> <p><b>網站版面名稱</b>: 提供廣告的網站和頁面。 </p> <p><b>傳送工具</b>: DoubleClick for Advertisers。 </p> <p><b>管道</b>: 橫幅廣告。 </p> <p><b>成本結構</b>: CPM、CPC 或固定，視廣告的成本結構而定。 </p> <p><b>創作名稱</b>: 與廣告/版面/創作 ID 相關聯之創作的名稱。 </p> <p><b>DFA &gt; SearchCenter 重複資料刪除</b>: 指定在 DFA 點進或閱覽發生時，DFA 應在 Searchcenter 變數中放入值。如需詳細資訊，請參閱 <a href="../../dfa-data-connector-analytics/dfa-integration-features.md#concept-ff93289d1662410e98f62c200394b3e3" format="dita" scope="local">SearchCenter 重複資料刪除</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 曝光數 </td> 
   <td colname="col3"> 接收 DFA 曝光數量度資料的自訂事件。曝光數會指出提供廣告的次數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 點按 </td> 
   <td colname="col3"> 選取會接收 DFA 點按量度資料的自訂事件。點按會指出訪客點按廣告的次數，如 DFA 的重新導向所計算。點按量度會與 Analytics 點進量度相關連。 <p>注意: 由於收集資料的方式有所差異，DFA 點按和 Analytics 點進可能不會完全相同。For more information, see <a href="../../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-metric-definitions.md#concept-2d5cd5ddd2594bb386a16a2764f30982" format="dita" scope="local"> Metric Definitions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 閱覽變數 </td> 
   <td colname="col3"> <p>接收 DFA 閱覽資料的 Analytics eVar。閱覽變數有助於您瞭解閱覽對您網站上的轉換率有何影響。 </p> <p>如同對 DFA 廣告變數所做的，Data connectors 會將相同的 DFA 相關分類新增至此 eVar (請見上方)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 前次檢視後經過的時間 (閱覽時間桶變數) </td> 
   <td colname="col3"> 接收「前次檢視後經過的時間」資料的 Analytics eVar。「前次檢視後經過的時間」會指出在前次廣告閱覽之後經過的時間長度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> 閱覽 </td> 
   <td colname="col3"> 接收 DFA 閱覽量度資料的自訂事件。使用具有閱覽變數的閱覽事件，可檢視哪些促銷活動並未直接促成點進，但在後續某個時間點對於網站流量的衍生具有一定的貢獻。 <p>Data connectors 會將選取的自訂事件重新命名為「閱覽」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> DFA 查詢失敗 </td> 
   <td colname="col3"> (可選) 接收任何回報的 DFA 失敗訊息代碼的 Analytics eVar。可能的 DFA 訊息代碼包括: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: 沒有 DoubleClick cookie。 </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: 使用者已退出。 </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: 沒有促銷活動歷史記錄。 </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: 查詢錯誤 (逾時、伺服器關閉等)。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> 逾時事件 </td> 
   <td colname="col3"> <p>會在每次 <span class="varname"> s. maxDelay </span> 計時器過期，且未從DFA伺服器接收回應。Use this event to configure the <span class="varname"> s.maxDelay </span> variable (see <a href="../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d" format="dita" scope="local"> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>


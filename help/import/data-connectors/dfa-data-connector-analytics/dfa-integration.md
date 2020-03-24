---
description: '要設定 DFA 整合，必須執行下列工作 '
keywords: DFA
title: DFA 整合
topic: Data connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# DFA 整合{#dfa-integration}

要設定 DFA 整合，必須執行下列工作:

## 設定 DFA 整合{#configure-the-dfa-integration}

逐步執行 DFA Data connectors 整合。

設定頁面會提供整合的概述，以及實用的相關資訊連結。此整合會同時產生 Adobe 和 DoubleClick 的相關費用。請連絡這兩個組織的適當銷售代表，並確定您瞭解費用結構。

1. 登入 [!DNL Adobe Analytics]。
1. 按一下&#x200B;**[!UICONTROL 「管理員」]**>**[!UICONTROL 「Data connectors」]**。

   ![](assets/data_connectors.png)

1. 找出 **[!UICONTROL DoubleClick DFA]**，然後按一下&#x200B;**[!UICONTROL 「新增」]**。

   ![步驟結果](assets/wizard-01.png)

   在「整合精靈」的每個頁面上提供必要資訊，然後按&#x200B;**[!UICONTROL 「下一步」]**。下表說明您透過此精靈完成整合所需的資訊。

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
   <td colname="col3"> <p>DFA 廣告主 ID 或父項 Floodlight 設定 ID。Data connectors 會使用此 ID 來識別要追蹤的 DFA 廣告主 (1.5 版的整合)。此廣告主 ID 無法用於 2.0 版的整合 - 將會查閱並使用父項 Floodlight 設定 ID。請參閱畫面上的指示 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA 廣告變數 </td> 
   <td colname="col3"> 接收 DFA 促銷活動屬性、曝光數和點按資料的 Analytics eVar。這通常是追蹤代碼 eVar (<span class="varname"> s.campaign </span>)，但您可以選擇任何可用的 eVar。Data connectors 也會將下列 DFA 相關分類新增至選取的 eVar: <p><b>促銷活動</b>: 一個提供給多個網站的廣告集合，可傳達一般訊息。 </p> <p><b>網站名稱</b>: 提供廣告的網站。 </p> <p><b>廣告名稱</b>: 廣告名稱，如您的 DFA 帳戶所定義。 </p> <p><b>網站版面名稱</b>: 提供廣告的網站和頁面。 </p> <p><b>傳送工具</b>: DoubleClick for Advertisers。 </p> <p><b>管道</b>: 橫幅廣告。 </p> <p><b>成本結構</b>: CPM、CPC 或固定，視廣告的成本結構而定。 </p> <p><b>創作名稱</b>: 與廣告/版面/創作 ID 相關聯之創作的名稱。 </p> <p><b>DFA &gt; SearchCenter 重複資料刪除</b>: 指定在 DFA 點進或閱覽發生時，DFA 應在 Searchcenter 變數中放入值。</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 曝光數 </td> 
   <td colname="col3"> 接收 DFA 曝光數量度資料的自訂事件。曝光數會指出提供廣告的次數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> 點按 </td> 
   <td colname="col3"> 選取會接收 DFA 點按量度資料的自訂事件。點按會指出訪客點按廣告的次數，如 DFA 的重新導向所計算。點按量度會與 Analytics 點進量度相關連。 <p>注意：由於收集資料的方式有所差異，DFA 點按和 Analytics 點進可能不會完全相同。  </a> </p> </td> 
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
   <td colname="col3"> <p>會在每次  <span class="varname"> s.maxDelay </span> 計時器到期、而未接收到來自 DFA 伺服器的回應時增量的 Analytics 計數器事件。使用此事件可設定 <span class="varname"> s.maxDelay </span> 變數調整 s.maxDelay </a>。) </p> </td> 
  </tr> 
 </tbody> 
</table>

## DFA 整合的網站更新{#web-site-updates-for-the-dfa-integration}

在 Genesis 為您設定 DFA 整合的分析報表套裝後，您必須執行下列作業設定您的網站和 DFA 環境，以支援整合:

### 驗證網域上的 Cookie 空間{#verify-cookie-space-on-the-domain}

DFA 的 Data connectors 整合會要求您在頁面的網域上設定一個 cookie。

雖然並不常見，但有些網域已達到部分網路瀏覽器的 cookie 容量上限。為避免影響到訪客在您網站上的瀏覽體驗，請洽詢您的網路操作、開發團隊或工程部門，以確認在用於 DFA 整合之頁面的網域上新增另一個 cookie，並不會影響到使用者體驗。您將必須選取 cookie 的名稱。

### 更新您的 DFA 查詢字串參數{#update-your-dfa-query-string-parameter}

如果您在使用 DFA 整合之前，已持續透過 Adobe Analytics 來追蹤廣告促銷活動，則所有的促銷活動 (電子郵件、搜尋或橫幅) 有可能使用相同的查詢字串參數來識別著陸頁面上的參照促銷活動 ID。

若想瞭解何時應從您 DFA 廣告促銷活動的 DFA 資料中要求閱覽和點進資料，Data connectors 必須識別出訪客在何時點按了 DFA 促銷活動橫幅廣告。為此，您必須將有所區分的查詢字串參數新增至 DFA 廣告促銷活動的登陸頁面 URL，使 Data connectors 能夠區分 DFA 廣告促銷活動頁面，與您在網站上可能會有的其他廣告促銷活動頁面。DFA 的 JavaScript 外掛程式中的 `dfa_overrideParam`。

>[!CAUTION]
>
>雖然促銷活動變數可用於其他促銷活動，但請勿將其用於 DFA 促銷活動。如果您將促銷活動變數設定為 DFA 促銷活動著陸頁面，Adobe 會無法將曝光數與點按繫結至 DFA 促銷活動點進。在每次造訪時，Adobe 收集伺服器都會在 DFA 伺服器中檢查是否有先前的點按或閱覽。因此，請僅於登陸頁面上納入 DFA 外掛程式代碼，以避免可能減緩頁面載入速度的非必要重新導向，對於網際網路連線速度較慢的使用者，更是如此。

## 更新網站的資料收集代碼{#update-your-web-site-s-data-collection-code}

DFA 的 Genesis 整合採用 DFA Floodlight 設定 ID (dfa_SPOTID)，這可以提升 DFA 與 Adobe 資料收集系統之間的報表一致性。

> [!NOTE] 在近期的 Google DFA 版本中，Spotlight 一詞已變更為 Floodlight。JavaScript 參數 `dfa_SPOTID` 是根據 Spotlight 術語而命名的，但用於兩個版本中。

若要在您的網站上啟用 DFA 整合，您必須新增下列項目，以更新您的 JavaScript 資料收集代碼:

* DFA 的整合模組
* 新增至您的收集代碼

### DFA 的整合模組 {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

DFA 整合採用 Adobe Experience Cloud 整合模組，可在您的核心 JavaScript 資料收集代碼 (`s_code.js`) 中新增功能。當您從「代碼管理器」下載「JavaScript 適用的 AppMeasurement」代碼時，整合模組會作為 .zip 檔案的一部分。請在您需要進一步協助尋找時，再聯絡您的 Adobe 顧問。

在您網站之 `s_code.js` 檔案的 `Modules` 區段中，插入整合模組代碼。

### 新增至您的收集代碼 {#section-8f98c727f1ba414fb8b4f02d696b8791}

Data connectors 會根據您在整合精靈中啟動 DFA 整合時所做的選取，產生對您 JavaScript 資料收集代碼的自訂新增項目，並透過電子郵件傳送給您。請在 `s_code.js` 檔案的主要區段中插入此代碼 (而不是插入至 `doPlugins` 函數或任何其他函數)。

下方顯示的範例代碼僅供說明之用；請使用您完成「Data connectors 整合精靈」之後透過電子郵件收到的代碼。

收集代碼由下列元件組成:

* DFA 整合設定
* 整合所需的外掛程式

**DFA 整合設定**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

DFA 整合設定區塊會設定 DFA 整合所需的變數。其中每個變數的值分別來自於下列來源:

**CSID**: 客戶端 ID。在您完成整合精靈後，隨即由 DFA 產生。Data connectors 會以您的 DFA CS ID 預先填入此變數，並且在您完成整合精靈後，透過設定電子郵件將此值傳送給您。如果您的帳戶啟用了「進階廣告服務」，則不需要此變數。

**SPOTID**: Floodlight 設定 (先前稱為 Spotlight ID)。Data connectors 會根據您在整合精靈中指定的 DFA 帳戶資訊，以您的 DFA Floodlight 設定 ID 預先填入此變數。

**tEvar**: 傳送變數。Data connectors 會以您在整合精靈中為閱覽變數指定的 Analytics 變數名稱，來預先填入此變數。在變更此值時，請務必使用 Adobe Engineering 或 Engineering 服務審慎協調。

**errorEvar**: 錯誤變數。Data connectors 會以您在整合精靈中為 DFA 查詢失敗變數指定的 Analytics 變數名稱，來預先填入此變數。

**timeoutEvent**: 逾時事件。Data connectors 會以您在整合精靈中為逾時事件變數指定的 Analytics 變數名稱，來預先填入此變數。

**requestURL**: 用來查詢廣告資訊的遠端 DFA 主機。未經 Adobe 的指示，請勿變更此值。

**maxDelay**: 指定 JavaScript 資料收集代碼等待 DFA Floodlight 伺服器發出回應的時間長度，以毫秒為單位。Adobe 建議您根據自己的網站流量，使用此值試驗出最適合的值。例如，增加此值通常可收集到較多 DFA 資料，但也會提高失去基本訪客資料的風險 (如果訪客在延遲時段內離開網站)。降低此值可減少失去點擊資料的風險，但可能也會減少與 Adobe 點擊資料一起傳送的 DFA 資料量。

**visitCookie**: 用來將 DFA 呼叫限定為每次造訪執行一次之 cookie 的名稱。

**clickThroughParam**: 一個查詢字串，通常包含在所有廣告中，用來通知整合模組有點按動作發生。查詢字串中若有此參數存在，則無論在過去 30 分鐘內是否查詢過訪客，都會執行對 DFA Floodlight 伺服器的要求。

**newRsidsProp**: (可選) 對應至未使用的流量屬性變數。DFA 整合會收集此值並將其存放在造訪 cookie 中，以識別對特定訪客收集資料的報表套裝。只有在使用 Adobe Engineering 服務進行自訂實施時，才需要此屬性。

**整合所需的外掛程式**

收集代碼新增項目加入了其他外掛程式，可改善 DFA 整合的作業效能:

* 將 DFA 查詢限定為每次造訪執行一次
* 提供 cookie 名稱彈性。雖然大部分的組織都使用 s_dfa，但對於 DFA 整合，您可以使用任何有效的 cookie 名稱。
* 消除非必要的重新導向。由於閱覽資料會以即時的方式收集，因此 Adobe 收集伺服器和 DFA 有可能會在每一次的頁面檢視交換資料。如果資訊不是必要的，外掛程式將會封鎖這些資料交換。

>[!CAUTION]
>
>外掛程式用來消除非必要 DFA 查詢的機制之一，是網域型造訪 cookie。如果訪客在 DFA 有所影響的閱覽或點進執行之後跨越了多個網域，跨越多個網域的整合報表套裝將會誇大點進和閱覽資料。

## 確認成功的 DFA 整合{#confirming-a-successful-dfa-integration}

在您完成所有必要的網站更新後，您可以使用 Charles*、Chrome Developer Tools 或 Firebug* 等網路流量檢視器，來確認 DFA 正在與 Adobe 收集伺服器通訊。

在您部署具有 DFA 功能的 `s_code.js` 檔案後，請使用網路流量檢視器來檢視 DFA 與 Adobe 資料收集伺服器之間的要求，並尋找下列項目:

* 對 DFA 的 `fls.doubleclick.net/json` 服務的要求。視您所使用的 DFA 版本之不同，此服務可能會以不同的方式回應。DFA 整合 1.5 版:

   * 以 [!DNL ad.doubleclick.net] 為目標的 HTTP 302 重新導向。這將會在回應時傳送一個「位置:」標記，其中包含廣告訪客的相關資訊。
   * 此「位置」標記會導致以 [!DNL integrate.112.2o7.net/dfa_echo] 為目標的重新導向。此服務會將廣告訪客的相關資訊轉譯為 JSON (JavaScript 物件標記法) 編碼字串。這項資料會連同「200 確定」HTTP 回應一起傳回。

* DFA 整合 2.0 版 (啟用「進階廣告服務」):

   * [!DNL fls.doubleclick.net] 會直接以「200 確定」回應。

在前述任一情況下，成功的要求都會產生包含參數 vX 的 Adobe 資料收集伺服器要求，其中，X 是您的閱覽 eVar 數字。此參數值採用下列格式: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX。此字串包含關於現行訪客的前次點按和前次曝光數的資料。

## 調整 s.maxDelay{#tuning-s-maxdelay}

要達到成功的 DFA 實施，必須針對您的網站將 s.maxDelay 最佳化。

一般而言，提高或降低 *`s.maxDelay`* 的決策，需在取得更多 DFA 訪客資料與危及 Adobe 訪客資料的收集之間作取捨。提升 *`s.maxDelay`* 將可取得較多 DFA 訪客資料，但 (若設定得太高) 可能會妨礙到 Adobe 訪客資料的收集。降低 s.maxDelay 可確保能夠收集 Adobe 訪客資料，但可能會失去 DFA 訪客資料。

*`s.maxDelay`*&#x200B;所包含的不僅止是連絡 DFA 時的網路通訊時間；它也代表瀏覽器在引發及評估這些通訊所依據之 JavaScript 時的延遲。這是因為，整合模組在將 HTML 元素插入 DOM (會從 DFA Floodlight 伺服器提取資料) 之後，就會開始 *`s.maxDelay`* 計時器。瀏覽器根據這個新的 HTTP 元素起始 HTML 要求實際花費的時間量，會隨著同時載入的其他影像或 JavaScript 檔案、訪客電腦的速度和特定的瀏覽器實施方式而有所不同。此外，在從 DFA Floodlight 伺服器擷取 JSON 資料時，瀏覽器必須要評估 JavaScript。這項作業同樣也完全由瀏覽器所控制，且若有大量的 JavaScript 代碼同時執行，或是有許多非同步的 JavaScript 要求，此作業則可能延遲。

請記住，*`s.maxDelay`*&#x200B;的設定必須要考量著陸頁面的複雜性，以及 DFA 的網路延遲量。在某些網站上，降低複雜性的可行方式之一是在頁面載入時即引發 Adobe 收集代碼，如此，在對 Floodlight 伺服器執行要求時，瀏覽器中的流量負載將會較輕。

在調整&#x200B;*`s.maxDelay`*&#x200B;時，逾時變數是絕對必要的，因為它會在每次達到 s.maxDelay 逾時的時候增量。在決定是否要提升或降低 *`s.maxDelay`* 時，我們建議依照此程序：

1. 收集 *`s.maxDelay`* 設為特定值的數天份資料。
1. 對時間範圍執行 [!DNL Daily Unique Visitors Report]。
1. 執行 [!DNL Timeout Event Report]，以查看已發生的逾時次數。請記住，對於每一個訪客只會收集一次逾時。

現在，請利用下圖計算

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

請注意，「逾時百分比」實際上會考量網站的所有訪客。其中有些訪客其實完全不會繫結至 DFA，因此逾時次數是失真的。為了改良此計算，另一種分析設定了 `clickThroughParam` (例如 `?CID=1`)，而僅考量造訪頁面的獨特訪客。此方式會有較高的精確性。

如果逾時百分比很低，請考慮降低&#x200B;*`s.maxDelay`*.如果很高，請增加 *`s.maxDelay`*.降低 *`s.maxDelay`* 時，您將需要重新執行 [!DNL Timeout Report] 以確定逾時次數並未急遽增加。提升 *`s.maxDelay`* 時，請執行 [!DNL Page Views Report] 以確保頁面檢視不會因資料遺失而流失。每次 *`s.maxDelay`* 有所變更時，請觀察資料數日，以確定資料代表的是趨勢，而不只是日常波動。

*`s.maxDelay`* 的最佳設定，是逾時百分比盡可能最小，而頁面檢視次數並未下降的平衡點。

當您移轉至 2.0 版的整合時，由於移除了 302 重新導向的關係，我們預期逾時次數將會降低。根據對測試版用戶端的初步觀察，逾時次數呈現穩定下降趨勢，收集到的 DFA 資料也因而增多

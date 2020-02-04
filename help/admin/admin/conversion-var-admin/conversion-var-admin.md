---
description: 自訂分析轉換變數 (或 eVar) 放置於您的網站上所選網頁的 Adobe 程式碼中。其主要作用是將自訂行銷報告中的轉換成功量度區段。eVar 可以瀏覽為準，其功能類似於 Cookie。傳送到 eVar 變數的值，會在預定的期間內跟隨使用者。
keywords: eVar
title: 轉換變數 (eVar)
topic: Admin tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# 轉換變數 (eVar)

自訂分析轉換變數 (或 eVar) 放置於您的網站上所選網頁的 Adobe 程式碼中。其主要作用是將自訂行銷報告中的轉換成功量度區段。eVar 可以瀏覽為準，其功能類似於 Cookie。傳送到 eVar 變數的值，會在預定的期間內跟隨使用者。

當 eVar 被設定為某個訪客的值，Adobe 會自動記住該值，直到其過期。訪客在 eVar 值活動期間遇到的任何成功事件都會被計入 eVar 值。

eVar 最適合用來測量原因和結果，如:

* 哪些內部促銷活動影響收入
* 哪些橫幅廣告最終產生註冊
* 下訂單前使用的內部搜尋次數

如果需要流量測量或路徑功能，建議使用流量變數。

> [!NOTE]影像要求的 eVar 中僅可儲存單一數值。如果 eVar 值中需要多個數值，建議您實施[清單變數 (list vars)](https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html)。

## 轉換變數 - 說明 {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

[編輯轉換變數](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md)時所用欄位相關說明。

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>元素 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 名稱 </span> </p> </td> 
   <td colname="col2"> <p>轉換變數的好記名稱。一般報告中會以此名稱來指稱 eVar，這也會是左側功能表中的報告名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 類型</span> </p> <p>(僅限 eVar) </p> </td> 
   <td colname="col2"> <p>變數值的類型: </p> <p> <b>文字字串</b>:</span> 擷取您網站上使用的文字值。這是最常用的 eVar 類型，也是預設設定。其運作方式與其他變數類似，包含的值是靜態文字字串。如果您要追蹤內部促銷活動或內部搜尋關鍵字等項目，建議使用此設定。 </p> <p> <b>計數器</b>:</span> 計算成功事件前一個動作發生的次數。例如，如果您使用 eVar 追蹤網站上的內部搜尋，設定此值為<span class="uicontrol">「文字字串」</span>可追蹤搜尋詞的使用情況。將此值設定為<span class="uicontrol">「計數器」</span>，可計算已執行搜尋的次數，不考慮所使用的搜尋詞。例如，您可使用計數器 eVar 來追蹤某個人在進行購買前，使用內部搜尋的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 配置 </span> </p> </td> 
   <td colname="col2"> <p>如果變數在事件之前接收到多個值，可決定 Analytics 如何為成功事件指派評價。支援的值包括: </p> <p> <b>最近</b>: 在該 eVar 過期以前，最近一個 eVar 值一律會收到成功事件的評分。 </p> <p> <b>原始值</b>: 在該 eVar 過期以前，第一個 eVar 值一律會收到成功事件的評分。 </p> <p> <b>線性</b>: 所有 eVar 值會收到均分的成功事件評分。實際僅在一次瀏覽中分發值，因此請搭配瀏覽的 eVar 過期時間使用線性配置。 </p> <p>附註: 切換分配至「線性」從「線性」切換分配時，不會顯示歷史資料。在報告介面混合配置類型可能造成報告中資料誤報。例如，「線性」配置將收入分配給數個不同的 eVar 值。變更回「最近」配置後，該收入的 100% 都關聯至最近的單一值。這種關聯會讓使用者產生不正確的結論。 </p> <p>為了避免報告產生混淆，Analytics 在介面中隱藏歷史資料。如果您決定將特定 eVar 變更回初始配置設定，仍可檢視這些歷史資料，但您不應僅為了存取歷史資料而變更 eVar 配置設定。如果想對已記錄的資料採用新的配置設定，Adobe 建議使用新的 eVar，而不是變更已建立了大量歷史資料的 eVar 之配置設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 過期時間</span> </p> </td> 
   <td colname="col2"> <p>指定時段或事件，在此時段或事件後 eVar 值就過期 (不再接收成功事件的評分)。如果成功事件發生在 eVar 過期後，「無」值會接收事件的評分 (沒有作用中的 eVar 值)。 </p> <p>如果您選取事件作為過期值，則變數在事件發生時才會過期。如果事件未發生，變數永遠不會過期。 </p> <p>可用的過期選項分為 4 種主要類別: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>在頁面檢視或瀏覽層級。</b>在頁面檢視或瀏覽以外轉換事件並不會關聯至 eVar。 </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>根據時段，如日、週、月或年。</b>在指定的時段以外轉換事件並不會關聯至 eVar。過期期間從設定變數時開始。eVar 的過期期限依其設定時間為準，計算至秒 (分鐘、小時、天、月等): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTE=60 秒 </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HOUR=3600 秒 (60 分鐘) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DAY=86400 秒 (24 小時) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">WEEK=604800 秒 (7 天) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MONTH=2678400 秒 (31 天) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">QUARTER=8035200 秒 (93 天 - 3 個 31 天的月份) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">YEAR=31536000 秒 (365 天) </li> 
      </ul> <p> </p> <p>如果某個造訪從星期一早上 7:00 開始，且在早上 7:15 於該造訪中設定 eVar，則其過期時間如下所示: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">當天過期: eVar 將於星期二早上 7:15 過期。 </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">當週過期: eVar 將於下星期一早上 7:15 過期。 </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">當月過期: eVar 將於星期一後第 31 天早上 7:15 過期。 </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>特定的轉換事件。</b>在指定的特定事件之後引發的任何其他轉換事件，都會關聯至 eVar。 </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>從不。</b>只要   <span class="varname">visitorID</span> Cookie 完整，在 eVar 和事件之間可間隔任何時間量。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 狀態</span> </p> <p>(僅限 eVar) </p> </td> 
   <td colname="col2"> <p>定義 eVar 狀態: </p> <p><b>停用</b>:</span> 停用 eVar。從轉換變數清單中移除 eVar。 </p> <p> <b>無子關聯</b>:</span> 可防止您依據子關聯劃分 eVar。 </p> <p> <b>基本子關聯</b>:</span> 可讓您依據任何包含完全子關聯 (例如「產品」或「促銷活動」) 的報表劃分 eVar。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 重設</span> </p> </td> 
   <td colname="col2"> <p>重設 eVar 中的任何現有值。 </p> <p>重新準備 eVar 時使用此設定，這樣您可以將舊值混合到新報告中。重設並不會清除歷史資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 銷售</span> </p> <p>(僅限 eVar) </p> </td> 
   <td colname="col2"> <p>銷售變數可遵循下列其中一種語法: </p> <p> <b>產品語法</b>:</span> 建立 eVar 值與產品的關聯。注意: 如果選取了「產品語法」，便會停用「銷售捆綁事件」區段，且無法選取並編輯。對於此語法，捆綁事件並不適用。 </p> </p> <p> <b>轉換變數語法</b>:</span> 僅在發生捆綁事件時才會建立 eVar 與產品的關聯。在這種情況下，您要選取作為捆綁事件的事件。 </p> <p>如果變更此設定但沒有相應地更新 JavaScript 程式碼，會導致資料遺失。請參閱<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/var_merchandising.html">銷售變數</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 銷售捆綁事件</span> </p> <p>(僅限 eVar) </p> </td> 
   <td colname="col2"> <p>如果「銷售」設定為<span class="uicontrol">轉換變數語法</span>，則選定的事件會將產品與目前的 eVar 值捆綁。 </p> <p>若要使用「捆綁事件」，請設定<span class="uicontrol">「配置」至「最近」</span>。如果<span class="uicontrol">「配置」是原始值</span>，則保留第一個 eVar 產品捆綁，直到 eVar 過期。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**過期**

`eVars` 會在經過您所指定的時段之後過期。eVar 過期後，即不會再獲得成功事件的評價。您也可以將 eVar 設定成隨著成功事件過期。例如，若您有某個內部促銷會在瀏覽結束時過期，此內部促銷將只會因為在購買或註冊啟動的瀏覽期間所發生的購買或註冊，而獲得評價。

有兩種方式可讓 eVar 過期: 

* 您可以將 eVar 設定成在指定的時段或事件之後過期。
* 您可以強制使 eVar 過期，這在重設變數用途時很適用。

若某個 eVar 在五月用來反映內部促銷情形，並在 21 天後過期，而在六月則用來擷取內部搜尋關鍵字，則您應在 6 月 1 日將此變數強制過期，或重設此變數。這麼做有助於將內部促銷值排除在六月的報表以外。

**區分大小寫**

eVar 不區分大小寫，但會以第一次出現時的大寫格式顯示。例如，若 eVar1 的第一個例項設為 &quot;Logged In&quot;，但後續所有的例項皆以 &quot;logged in&quot; 的格式傳入，則報表一律會將 eVar 的值顯示為 &quot;Logged In&quot;。

**計數器**

eVar 通常會用來放置字串值，但也可設定作為計數器。當您嘗試計算使用者在某個事件之前所執行的動作數時，即可將 eVar 當作計數器使用。例如，您可以使用 eVar 擷取購買之前的內部搜尋次數。每次訪客搜尋時，eVar 中都應會有 &#39;+1&#39; 值。若訪客在購買之前做了四次搜尋，您將會看見各個總計數的例項: 1.00、2.00、3.00、4.00。但只有 4.00 會獲得購買事件的評價 (訂購和收入度量)。eVar 計數器的值必須是正數。
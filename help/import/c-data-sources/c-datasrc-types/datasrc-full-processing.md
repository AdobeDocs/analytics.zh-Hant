---
description: 針對以標準伺服器調用 (「通用 > 完全處理」) 處理資料，資料來源支援下列變數。
subtopic: Data sources
title: 完全處理
topic: Developer and implementation
uuid: 590ae89c-6e17-453b-b701-ce1adbea6fa4
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 完全處理

針對以標準伺服器調用 (「通用 > 完全處理」) 處理資料，資料來源支援下列變數。

「完全處理」資料來源的資料處理方式，會將資料當做在指定的時間由 Adobe 伺服器收到 (每次點擊都有時間戳記)。

* [訪客資料](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_6065627D0C144506965F562C80AE67F8)
* [欄參考](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#section_92BAE76639E3404E97276B1BE0581078)

## 訪客資料 {#section_6065627D0C144506965F562C80AE67F8}

「完全處理」資料來源的資料是使用不同的訪客個人資料進行處理，因此即使上傳資料中的訪客 ID 與使用 JavaScript 或其他 AppMeasurement 程式庫收集的資料相符，也不會從 eVar 配置的角度連結訪客個人資料。

例如，訪客 ID 為 `"user@example.com"` 的使用者從名為「Spring Sale」(此名稱儲存在 campaign 變數) 的促銷活動造訪您的網站。如果您稍後使用相同的訪客 ID 上傳交易，&quot;Spring Sale&quot; 促銷活動不會收到任何使用完全處理資料來源上傳之收入或成功事件的信用。

## 欄參考 {#section_92BAE76639E3404E97276B1BE0581078}

<table id="table_AAC04491D643467B9C80FDEF88130B13"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript 變數 </th> 
   <th colname="col2" class="entry"> 完全處理欄變數 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>campaign </p> </td> 
   <td colname="col2"> <p>campaign </p> </td> 
   <td colname="col3"> <p>轉換促銷活動追蹤代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>channel </p> </td> 
   <td colname="col2"> <p>channel </p> </td> 
   <td colname="col3"> <p>渠道字串 (如體育版)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>currencyCode </p> <p>注意：標準資料來源也支援此變數作為 <code> currency code </code>。 </p> </td> 
   <td colname="col3"> <p>收入貨幣代碼 (如 USD)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timestamp </p> </td> 
   <td colname="col2"> <p>日期 </p> </td> 
   <td colname="col3"> <p>使用 ISO 8601 日期格式 <code> YYYY-MM-DDThh:mm:ss±UTC_offset </code> (如 <code> 2013-09-01T12:00:00-07:00 </code>) 或 Unix 時間格式 (自 1970 年 1 月 1 日起的總秒數)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar<i>N</i> </p> </td> 
   <td colname="col2"> <p>eVar<i>N</i>，即 &lt;eVar2&gt;…&lt;/eVar2&gt; </p> </td> 
   <td colname="col3"> <p>轉換 eVar 名稱。您最多可以有 75 個 eVar (<span class="varname"> eVar1</span> - <span class="varname">eVar75 </span>). </p> <p>您可指定 eVar 名稱 (eVar12) 或友好名稱 (廣告促銷活動 3)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>events </p> </td> 
   <td colname="col2"> <p>events </p> </td> 
   <td colname="col3"> <p>事件字串，格式語法與 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html"  >s.events</a> 變數相同。 </p> <p>例如: </p> 
    <code>
      scAdd,event1,event7 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hier<i>N</i> </p> </td> 
   <td colname="col2"> <p>hier<i>N</i>，即 &lt;hier2&gt;…&lt;/hier2&gt; </p> </td> 
   <td colname="col3"> <p>階層名稱。您最多可以有 5 個階層 (<span class="varname"> hier1</span> - <span class="varname">hier5 </span>). </p> <p>您可指定預設階層名稱 (<span class="varname">hier2</span>) 或友好名稱 (<span class="term">洋基</span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkName </p> </td> 
   <td colname="col2"> <p>linkName </p> </td> 
   <td colname="col3"> <p>連結名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkType </p> </td> 
   <td colname="col2"> <p>linkType </p> </td> 
   <td colname="col3"> <p>連結的類型。支援的值包括: </p> 
    <ul id="ul_E441013055A9447AB6C3FB05B6099F7D"> 
     <li id="li_A33F66F30B60479284F72AE3AD4BF499"> <b>d</b>: 下載連結 </li> 
     <li id="li_182F695AA2D044DAB036BAFE38BC3915"> <b>e</b>: 外部連結 </li> 
     <li id="li_4FD4D542D1774607860BEF41C1B090D1"> <b>o</b>: 自訂連結 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>linkURL </p> </td> 
   <td colname="col2"> <p>linkURL </p> </td> 
   <td colname="col3"> <p>連結的 HREF。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageName </p> </td> 
   <td colname="col2"> <p>pageName </p> </td> 
   <td colname="col3"> <p>頁面名稱 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageType </p> </td> 
   <td colname="col2"> <p>pageType </p> </td> 
   <td colname="col3"> <p>頁面類型 (「錯誤頁面」)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>pageURL </p> </td> 
   <td colname="col2"> <p>pageURL </p> </td> 
   <td colname="col3"> <p>頁面 URL (如 <code>https://www.mysite.com/index.html)</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>products </p> </td> 
   <td colname="col2"> <p>products </p> </td> 
   <td colname="col3"> <p>產品清單 (如 <code> "Sports;Ball;1;5.95") </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prop1 - prop75 </p> </td> 
   <td colname="col2"> <p>prop<i>N</i>，即 &lt;prop2&gt;…&lt;/prop2&gt; </p> </td> 
   <td colname="col3"> <p>屬性編號字串 (如  <span class="term"> 體育版 </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchaseID </p> </td> 
   <td colname="col2"> <p>purchaseID </p> </td> 
   <td colname="col3"> <p>購買 ID 號碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>s_account </p> </td> 
   <td colname="col2"> <p>reportSuiteID </p> </td> 
   <td colname="col3"> <p>要貢獻點按的報表套裝 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server </p> </td> 
   <td colname="col2"> <p>server </p> </td> 
   <td colname="col3"> <p>伺服器字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>state </p> </td> 
   <td colname="col2"> <p>state </p> </td> 
   <td colname="col3"> <p>轉換州字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zip </p> </td> 
   <td colname="col2"> <p>zip </p> </td> 
   <td colname="col3"> <p>轉換郵遞區號。 </p> </td> 
  </tr> 
 </tbody> 
</table>

下表列出使用 JavaScript 程式庫時會自動填充的流量奱數。這些屬性沒有相關聯的變數，但可以用資料來源匯入。

<table id="table_FDBC5BD225644AA09078C0570BE709FE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>完全處理欄變數 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>browserHeight </p> </td> 
   <td colname="col2"> <p>瀏覽器高度 (以像素為單位，如 768)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>browserWidth </p> </td> 
   <td colname="col2"> <p>瀏覽器寬度 (以像素為單位，如 1024)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charSet </p> </td> 
   <td colname="col2"> <p>您的網站支援的字元集。如 UTF-8、ISO-8859-1 等等。 </p> <p>如需完整清單，請參閱「<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/index.html"  >多位元組字元集</a> (國際化)」白皮書。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickAction </p> </td> 
   <td colname="col2"> <p>訪客點擊地圖的物件識別碼 (OID) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickActionType </p> </td> 
   <td colname="col2"> <p>訪客點擊地圖的物件識別碼類型 (OIDT) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContext </p> </td> 
   <td colname="col2"> <p>訪客點擊地圖的頁面識別碼 (PID) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickContextType </p> </td> 
   <td colname="col2"> <p>訪客點擊地圖的頁面識別碼類型 (PIDT) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickSourceID </p> </td> 
   <td colname="col2"> <p>訪客點擊地圖的來源索引 (OI) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clickTag </p> </td> 
   <td colname="col2"> <p>訪客點擊地圖的物件標記名稱 (OT) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>colorDepth </p> </td> 
   <td colname="col2"> <p>監視器色彩深度 (以位元為單位，如 24)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>connectionType </p> </td> 
   <td colname="col2"> <p>訪客的連線類型 ( <span class="term"> LAN </span> 或是 <span class="term"> 數據機 </span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cookiesEnabled </p> </td> 
   <td colname="col2"> <p>Y 或 N -- 訪客是否支援 first party 作業 cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>currencyCode </p> </td> 
   <td colname="col2"> <p>您的網站使用的預設貨幣代碼。 </p> <p>例如，USD = 美元、EUR = 歐元、JPY = 日圓等等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>homePage </p> </td> 
   <td colname="col2"> <p>Y 或 N -- 目前頁面是否為訪客的首頁。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaEnabled </p> </td> 
   <td colname="col2"> <p>Y 或 N -- 訪客是否已啟用 Java。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javaScriptVersion </p> </td> 
   <td colname="col2"> <p>JavaScript 版本 (如 1.3)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>plugins </p> </td> 
   <td colname="col2"> <p>瀏覽器外掛程式名稱清單，以分號隔開。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>propN </p> </td> 
   <td colname="col2"> <p>您的屬性的屬性值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>referrer </p> </td> 
   <td colname="col2"> <p>頁面反向連結的 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resolution </p> </td> 
   <td colname="col2"> <p>螢幕解析度 (如 1024x768)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>scXmlVer </p> </td> 
   <td colname="col2"> <p>行銷報表 XML 請求版本編號 (如 1.0)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>timezone </p> </td> 
   <td colname="col2"> <p>訪客所在時區與格林威治時間的小時差 (如 -8)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorID </p> </td> 
   <td colname="col2"> <p>訪客 ID 號碼。 </p> </td> 
  </tr> 
 </tbody> 
</table>


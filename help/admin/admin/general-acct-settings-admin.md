---
description: 「管理」報表套裝裡「一般帳戶設定」的欄位說明。
seo-description: 「管理」裡報表套裝「一般帳戶設定」的欄位說明。
seo-title: 一般帳戶設定
solution: Analytics
title: 一般帳戶設定
topic: 管理工具
uuid: c1ab5c34-2c41-4d12-a706-0e760 dff a95
translation-type: tm+mt
source-git-commit: 01ac0011f2e47e6798a520df8ffe5d8393ac0c3c

---


# 一般帳戶設定

「管理」報表套裝裡「一般帳戶設定」的欄位說明。

**[!UICONTROL 「分析]** &gt; **[!UICONTROL 管理]** &gt; **[!UICONTROL 報表套裝]** &gt; **[!UICONTROL 編輯設定]** &gt; **[!UICONTROL 一般]** &gt; **[!UICONTROL 一般帳戶設定」]**

這些設定包含基本報表套裝功能的編輯選項，例如名稱與時區。

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 網站標題</span> </td> 
   <td colname="col2"> <p>識別您的網站。請提供每個報表套裝唯一的網站標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基礎 URL</span> </td> 
   <td colname="col2"> <p>指定報表套裝的主要網站。基本 URL 不會影響反向連結篩選。請改用<a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local">內部 URL 篩選器</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 時區</span> </td> 
   <td colname="col2"> <p>判斷與您的報告資料相關的日期和時間。 </p> <p>變更動態報表套裝上的時區，會在報告資料中產生尖峰或間隙。為了降低影響，Adobe 建議在非尖峰時刻變更時區，以免出現資料偏差。 </p> <p>例如，如果您在下午 3:00 將報表套裝時區從中部時間改為太平洋時間，則報表套裝的目前時間便會變為太平洋時間下午 1:00。由於報告已收集了 1:00 的資料，因此報告會在下午 1:00 至 3:00 之間顯示一段流量尖峰。 </p> <p>此外，如果您在下午 3:00 將報表套裝時區從中部改為東部，則報表套裝的目前時間會變為東部下午 4:00。報告在變更時間的當天下午 3:00 至 4:00 之間，將不會顯示任何資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 轉換級別</span> </td> 
   <td colname="col2"> <p> 啟用或停用如 eVar 和促銷活動之類的電子商務變數。如果您的網站上無購物車，可使用<span class="uicontrol">「已啟用，無購物車」</span>選項，以隱藏所有的購物車報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 預設頁面</span> </td> 
   <td colname="col2"> <p> 若您的<span class="wintitle">最受歡迎頁面報告</span>包含 URL 而非頁面名稱，此設定可防止多個 URL 代表同一頁面的情形。For example, the URLs <span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove default filenames so that these two URLs would both show up as <span class="filepath"> https://mysite.com</span>. </p> <p>若保留為空白，則會從 URL 中移除下列檔案名稱: <span class="filepath">index.htm</span>、<span class="filepath">index.html</span>、<span class="filepath">index.cgi</span>、<span class="filepath">index.asp</span>、<span class="filepath">default.htm</span>、<span class="filepath">default.html</span>、<span class="filepath">default.cgi</span>、<span class="filepath">default.asp</span>、<span class="filepath">home.htm</span>、<span class="filepath">home.html</span>、<span class="filepath">home.cgi</span> 與 <span class="filepath">home.asp</span>。 </p> <p>要完全停用檔案名稱移除，請輸入一個絕不會出現在 URL 中的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 將 IP 位址的最後八位數字取代為 0 </span> </td> 
   <td colname="col2"> <p>先移除最後的八位數字，再進行 IP 篩選。因此，最後八位數字被 0 取代，而 IP 排除規則應更新為符合最後為零的 IP 位址。符合 * 應符合 0。 </p> <p>選取此選項表示 IP 位址在處理前已先變更。例如，IP 位址 134.123.567.780 會變更為 134.123.567.0。地域劃分資料不會像使用整個 IP 位址一樣準確。具體而言，城市準確度會比國家/地區或地區準確度更受影響。機器人規則和 VISTA 規則都會受影響，因為它們無法使用整個 IP 位址。此外，基於 IP 的處理規則 (包括行銷管道規則和報表套裝處理規則) 也會受到此設定影響。 </p> <p>注意: 2019 年 1 月後，在倫敦資料中心新建的所有報表套裝都會預設啟用這項設定，且僅限從 Admin Console 所列範本複製而來的報表套裝設定。若報表套裝的設定是複製自其他報表套裝，則會繼承所選報表套裝的所有設定。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> IP 模糊化</span> </td> 
   <td colname="col2"> <p>將 IP 位址轉變為無法辨識的字串，實際上是將其從 Adobe 資料儲存區中移除。啟用「IP 模糊化」後，原始的 IP 位址將會永久遺失。 </p> <p>注意: Analytics 中每一處的 IP 位址都會模糊化，包括 Data Warehouse。不過，Target 中的 IP 設定則另外控制，因此此設定不會影響 Target。 </p> <p>若啟用 IP 模糊化，會在 IP 位址被模糊化前即排除 IP，因此當客戶啟用 IP 模糊化時不必變更任何東西。 </p> <p>勾選「<span class="uicontrol">停用</span>」會在資料中保留 IP 位址。 </p> <p>勾選「<span class="uicontrol">模糊化 IP </span>」會將 IP 變更為雜湊值 (例如 234abc6493872038)。 </p> <p>勾選「<span class="uicontrol">移除 IP 位址</span>」會在地理查閱後，將資料中的 IP 位址更換為 x.x.x.x。 </p> <p>注意：此設定可能需要變更自訂 <a href="../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> 機器人規則</a> 或<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"> IP排除</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 交易 ID 儲存</span> </td> 
   <td colname="col2"> <p>讓您能夠使用「<a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID" format="https" scope="external">交易 ID</a>」資料來源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> 啟動 Ad Hoc Analysis</span> </td> 
   <td colname="col2"> <p>指出在 Ad Hoc Analysis 是否將該報表套裝顯示為可用的報表套裝。使用此設定限制哪些報表套裝要顯示為 Ad Hoc Analysis 的選項。例如，您可停用 Ad Hoc Analysis 的開發和 QA 報表套裝。 </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> 啟用 Data Warehouse</span> </td> 
   <td colname="col2"> <p>啟用<span class="uicontrol">「工具</span> &gt;<span class="uicontrol"> Data Warehouse」</span>底下的 Data Warehouse UI。 </p> </td> 
  </tr> 
 </tbody> 
</table>


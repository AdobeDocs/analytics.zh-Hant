---
description: 下表列出查詢參數，這些參數包含每個傳送給資料收集之分析變數的值。
keywords: Analytics 實施
seo-description: 下表列出查詢參數，這些參數包含每個傳送給資料收集之分析變數的值。
seo-title: 資料收集查詢參數
solution: Analytics
title: 資料收集查詢參數
topic: 開發人員和實施
uuid: 4d5af486-df27-42Fe-bb9 c-28938ddf2 b2
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# 資料收集查詢參數

下表列出查詢參數，這些參數包含每個傳送給資料收集之分析變數的值。

這項資訊可用於使用[封包分析器](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258)、手動建立影像請求時或使用 [動態變數](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262)時。

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> 參數 </th> 
   <th class="entry"> Analytics 變數 </th> 
   <th class="entry"> 填入報表 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> 無 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> 觀眾管理員位置提示 (用於 Experience Cloud 共用設定檔整合) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> 無 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> 觀眾管理員 Blob (用於 Experience Cloud 共用設定檔整合) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輔助 </td> 
   <td colname="col2"> 無 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> Analytics 訪客 ID </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 表示影像請求的起始處。 </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 表示影像請求的結束處，意指請求並未被裁截。 </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 瀏覽器高度 </td> 
   <td> 瀏覽器視窗高度 (像素) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 瀏覽器寬度 </td> 
   <td> 瀏覽器視窗寬度 (像素) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 監視器色彩深度 </td> 
   <td> 色彩品質 (位元） </td> 
  </tr> 
  <tr> 
   <td> <code> c. <span class="varname"> [key] </code></span> </td> 
   <td> <p>s.contextData </p> </td> 
   <td> <p>無 </p> </td> 
   <td> <p>以下列其中一種格式指定索引鍵-值對: </p> <p> <code> &lt;my.a&gt;red&lt;/my.a&gt; </code> </p> <p>或: </p> <p> <code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code> </p> <p>這些範例會產生 <code>my.a = red</code> 的上下文資料值。可以指定多個索引鍵-值對。 </p> <p>In the query string, this context data variable would appear as <code> c.&amp;my.a=red </code> </p> </td> 
  </tr> 
  <tr> 
   <td> c1 - c75 </td> 
   <td> s.prop1 - s.prop75 </td> 
   <td> 所有自訂流量報表 </td> 
   <td> 自訂流量報表中使用的流量變數 </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s.currencyCode </td> 
   <td> 無 </td> 
   <td> 網站上使用的貨幣類型 </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s.cookieDomainPeriods </td> 
   <td> 無 </td> 
   <td> 表示追蹤 Cookie 的網域中的時段數目；手動設定。 </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s.charSet </td> 
   <td> 無 </td> 
   <td> 影像請求的字元編碼 </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s.cookieLifetime (以秒為單位的 s_vi cookie 存留期) </td> 
   <td> 無 </td> 
   <td> 訪客 Cookie 的期限。 </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s.channel </td> 
   <td> 網站內容 | 網站區域 </td> 
   <td> 流量報表中使用的網站區域變數 </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> 點擊類型 </td> 
   <td> 點擊類型 </td> 
   <td> 表示行為屬於前景直接互動的結果，或是裝置在沒有背景直接互動的情況下所傳送的資料。 </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 連線類型 </td> 
   <td> 連線類型 (數據機、LAN 等；只能在 IE 瀏覽器中填入) </td> 
  </tr> 
  <tr> 
   <td> <code> D </code> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> 無 </td> 
   <td> <p>請參閱 <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> 動態變數 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> events 或 ev </td> 
   <td> s.events </td> 
   <td> 網站流量 | 購買、購物車、自訂事件 </td> 
   <td> 發生在頁面上的商務和自訂事件；用於轉換報表 </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 目前頁面的 URL，最多 255 個位元組。 </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 長度超過 225 個位元組的 URL 會被切割，前 255 個位元組出現在 g 參數中，其餘位元組出現在 -g= 查詢參數的查詢字串中。 </td> 
  </tr> 
  <tr> 
   <td> h1 - h5 </td> 
   <td> s.hier1 - s.hier5 </td> 
   <td> 網站內容 | 階層報表 </td> 
   <td> 階層變數；用於流量報表 </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 訪客首頁 </td> 
   <td> 表示目前頁面是否為瀏覽器的首頁 (Y 或 N；只能在 IE 瀏覽器中填入) </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | Javascript 版本 </td> 
   <td> 顯示目前安裝的 Javascript 版本 (通常是 1.x) </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | Cookie </td> 
   <td> Cookie 是否受瀏覽器支援 (Y、N 或 U) </td> 
  </tr> 
  <tr> 
   <td> l1-l3 </td> 
   <td> s.list1-s.list3 </td> 
   <td> 自訂轉換 </td> 
   <td> 使用分隔字元的值清單，在傳給變數之後，會報告為個別的行項目以供製作報告。 </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> Experience Cloud 訪客 ID </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 表示影像請求是否源自 JS 檔案 (1 或 0) </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s.visitorNameSpace </td> 
   <td> 無 </td> 
   <td> 指定設定 Cookie 的網域 </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s.objectID </td> 
   <td> 網站內容 | 連結 | ClickMap </td> 
   <td> 最後一頁的物件識別碼；用於 ClickMap </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> 無 </td> 
   <td> 網站內容 | 連結 | ClickMap </td> 
   <td> 最後一頁的物件標記名稱；用於 ClickMap </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | Netscape 外掛程式 </td> 
   <td> 以分號分隔的瀏覽器外掛程式名稱 </td> 
  </tr> 
  <tr> 
   <td> pageName (或 gn) </td> 
   <td> s.pageName </td> 
   <td> 網站內容 | 頁面 </td> 
   <td> 報表中的頁面指定名稱 </td> 
  </tr> 
  <tr> 
   <td> pageType (或 gt) </td> 
   <td> s.pageType </td> 
   <td> 網站內容 | 找不到頁面 </td> 
   <td> 表示是否為 404 頁面 (為 'error' 或空白) </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 只會對新訪客發生；防止無限的重導操作 (永遠為 true) </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s.linkType </td> 
   <td> 網站內容 | 連結 | 退出連結、檔案下載、自訂連結 </td> 
   <td> 決定啟動的自訂連結點擊類型 </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> 無 </td> 
   <td> 網站內容 | 連結 | 退出連結、檔案下載、自訂連結 </td> 
   <td> 發生自訂連結點擊的 URL </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> 無 </td> 
   <td> 網站內容 | 連結 | 退出連結、檔案下載、自訂連結 </td> 
   <td> 自訂連結友好名稱 </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> 無 </td> 
   <td> 所有視訊報表 </td> 
   <td> 用於追蹤舊版視訊報表中的里程碑；於 v15 廢除 </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 僅限 Adobe 使用。不可變更。 </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> 無 </td> 
   <td> 網站內容 | 連結 | ClickMap </td> 
   <td> 最後一頁的頁面識別碼；用於 ClickMap </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> 無 </td> 
   <td> 網站內容 | 連結 | ClickMap </td> 
   <td> 最後一頁的頁面識別碼類型；用於 ClickMap </td> 
  </tr> 
  <tr> 
   <td> products (或 pl) </td> 
   <td> s.products </td> 
   <td> 產品 | 產品 </td> 
   <td> 用於轉換報表中的產品變數 </td> 
  </tr> 
  <tr> 
   <td> purchaseID (或 pi) </td> 
   <td> s.purchaseID </td> 
   <td> 無 </td> 
   <td> 用於刪除重複的購買，防止收入膨脹 </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> 所有流量來源報表 </td> 
   <td> 反向連結 URL </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 螢幕解析度 </td> 
   <td> 螢幕解析度 (寬度 x 高度) </td> 
  </tr> 
  <tr> 
   <td> server (或 sv) </td> 
   <td> s.server </td> 
   <td> 網站內容 | 伺服器 </td> 
   <td> 頁面的伺服器；用於流量報表 </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s.state </td> 
   <td> 訪客資料 | 訪客狀態 </td> 
   <td> 請依照變數所定義內容指定訪客狀態。 </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> (自動，每次點擊時傳送，沒有自訂的時間戳記) </td> 
   <td> 無 </td> 
   <td> <p><code>t</code> 參數為以下格式: </p> 
    <code>dd/mm/yyyy&amp; amp；nbsp；hh：mm：ss&amp; amp；nbsp；D&amp; amp；nbsp；偏移量 </code>
  <p>其中 D 是 <code>0-6</code> 範圍中的數字，指定一星期的天數，而 <code>OFFSET</code> 代表: </p> 
    <code>偏移與安培；nbsp；從與amp；nbsp；GMT&amp; amp；nbsp；進出；nbsp；小時與月；nbsp；*&amp; amp；nbsp；60&amp; amp；nbsp；*&amp; amp；nbsp；&amp; amp；nbsp；1 </code>
  <p> 例如: </p> 
    <code>23/09/2016&amp; amp；nbsp；14：00：00&amp; amp；nbsp；&amp; amp；nbsp；420 </code>
  </td> 
  </tr> 
  <tr> 
   <td> <code> ts </code> </td> 
   <td> <p>時間戳記 </p> </td> 
   <td> 無 </td> 
   <td> <p>每次點擊時計算及傳送的自訂時間戳記。通常用於離線追蹤。 </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | Java </td> 
   <td> 啟用 Java (Y 或 N) </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> 促銷活動 | 追蹤代碼 </td> 
   <td> 轉換報表中使用的 campaign 變數 </td> 
  </tr> 
  <tr> 
   <td> v1 - v75 </td> 
   <td> s.eVar1-s.eVar75 </td> 
   <td> 所有自訂轉換報表 </td> 
   <td> 用於自訂轉換報表的轉換變數 </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> 無 </td> 
   <td> 訪客的獨特識別碼設定在 訪客 ID 變數. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s.vmk </td> 
   <td> 無 </td> 
   <td> 訪客移轉金鑰；用於從第三方 Cookie 移轉到第一方 Cookie。不再提倡。 </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s.variableProvider </td> 
   <td> 無 </td> 
   <td> 用於 Genesis 整合 </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s.transactionID </td> 
   <td> 無 </td> 
   <td> 用於將線上資料連結至離線資料的交易 ID </td> 
  </tr> 
  <tr> 
   <td> 郵遞區號 </td> 
   <td> s.zip </td> 
   <td> 訪客資料 | 訪客郵遞區號 </td> 
   <td> 決定郵遞區號由變數定義 </td> 
  </tr> 
  <tr> 
   <td> 在影像請求 URL 中，/5/ (適用於行動通訊協定) 或 /1/ (適用於非行動通訊協定)。 </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> <p> 控制使用 Cookie 和其他方法來識別訪客的順序。 </p> </td> 
  </tr> 
 </tbody> 
</table>


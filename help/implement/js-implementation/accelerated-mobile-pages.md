---
description: 在 Adobe Analytics 實施 Accelerated Mobile Pages (AMP) 專案。
keywords: Analytics Implementation;amp;amp-analytics;adobeanalytics template;adobeanalytics_nativeConfig template;click tracking;visitor inflation;id service
title: Accelerated Mobile Pages
topic: Developer and implementation
uuid: c86e4a80-7191-4ee7-ab20-787730026c4b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Accelerated Mobile Pages

在 Adobe Analytics 實施 Accelerated Mobile Pages (AMP) 專案。

AMP 是一項[開放原始碼專案](https://www.ampproject.org/)，可讓您建立快速轉譯靜態內容的網頁。這項功能相當適合發佈者使用，因為他們只需建立一次行動最佳化內容，即可在任何地方立即載入。包含主題:

* [運作方式](/help/implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [使用有「adobeanalytics」範本的 amp-analytics 標記](/help/implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [使用有「adobeanalytics_nativeConfig」範本的 amp-analytics 標記](/help/implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [摘要](/help/implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [常見問題集](/help/implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**其他文件及範本**

* 外部的共有資源 AMP 專案[文件](https://www.ampproject.org/docs/get_started/about-amp.html)
* 設定[範本](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)

## 運作方式 {#section_21C2836D63104794BCEBEECB6593AFBF}

AMP 有特別標記的 HTML 頁面，儲存於網路各處包含參與的技術合作夥伴與供應商的不同內容傳遞網路 (CDN)。如此一來，AMP 內容就能從最近的可能來源以最少的潛在因素供應。這造成了分析的難題，因為您永遠不能 100% 確定發佈者的內容會從哪裡載入，而且第三方的小型文字檔案也會擾亂訪客識別。

此外，為求徹底減少頁面比重並加快頁面載入速度，AMP 限制 JavaScript 及小型文字檔案的使用。這就您的行動裝置來說是項優勢，因為可以減少處理量，但也由於不易精確測量出不重複訪客及瞭解贏取與保留使用者的情形，而造成難題。

為解決這些問題，Adobe 和 AMP 合作夥伴及發佈者在兩個選項上同心協力，兩個選項都使用 `amp-analytics` 標記，讓發佈者能從中選擇出最合乎其商業需求者。第一種方式是使用 `"adobeanalytics"` 追蹤範本，以便直接從 AMP 內建立 Analytics 要求。第二種方式是使用 `"analytics_nativeConfig"` 追蹤範本，這種方式會使用 iframe，其中包含您部署在一般網站上的 AppMeasurement 程式碼。以下表格提供參考，讓您能初步瞭解兩種方法各自的得失利弊。

|  | **「adobeanalytics」範本** | **「adobeanalytics_nativeConfig」範本** |
|---|---|---|
| (在現有的報表套裝) 訪客或訪客計數 | 高度膨脹 | 最小膨脹 |
| 使用個別報告套裝 | 建議 | 非必要 |
| 全新 vs. 回頭的訪客 | 不支援 | 支援 |
| 訪客 ID 服務 | 不支援 | 支援 |
| 視訊與連結追蹤 | 部分支援 | 尚未支援 |
| 實施困難 | 有些困難 | 相對容易 |
| [!DNL Experience Cloud] 整合 | 不支援 | 支援警告功能 |

## 使用有「adobeanalytics」範本的 amp-analytics 標記 {#section_2E4EBF4EF623440D95DE98E78C47244E}

`"adobeanalytics"` 追蹤範本利用 `amp-analytics` 標籤直接建立追蹤請求。若您在 `amp-analytics` 標籤中使用 `"adobeanalytics"` 範本，您可以明確指定出在特定頁面事件中的熱門請求，例如使頁面可見或者按一下就能開啟 (未來將可在播放視訊或其他模式中開啟頁面)。點擊事件可以量身打造，明確指定選取器，以適用於特定元素 ID 或等級。Adobe 使用專為 [!DNL Adobe Analytics] 量身打造的 `"adobeanalytics"` 範本，讓設定更容易。您可以將 `type="adobeanalytics"` 新增到 amp-analytics 標籤以載入範本。

在以下的程式碼範例中，有兩個已定義的觸發器: `pageLoad` 和 `click`。文件可見時，`pageLoad` 觸發器就會立即啟動，並包含 `vars section` 中定義的 `pageName` 變數。第二個觸發器 `click` 則會於按鈕點擊後立即啟動。將使用值 `button clicked` 設定 `eVar 1` 以用於此事件。

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
      "reportSuites": "reportSuiteID", 
      "pageName": "Adobe Analytics Using amp-analytics tag" 
  }, 
    "triggers": { 
      "pageLoad": { 
        "on": "visible", 
        "request": "pageView" 
      }, 
      "click": { 
        "on": "click", 
        "selector": "button", 
        "request": "myClick", 
        "vars": { 
          "eVar1": "button clicked" 
        } 
      } 
    } 
  } 
  </script> 
  </amp-analytics> 
```

在 `click` 觸發器中，您可以明確指定一個選取器，不論何時點擊特定 DOM 元素 (在此為任何按鈕)，`buttonClick` 要求都會立即啟動，且會自動設定，將此點擊指稱為非階段事件 (即 `trackLink` 呼叫)。

此外，`amp-analytics` 也支援一些變數替代，讓 AMP 能提供已知的資料數值。您可以造訪 [amp-analytics 變數文件](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)以獲得更多資訊。

請注意，若您想併入任何技術或 DOM 變數 (例如瀏覽器、螢幕大小、裝置、反向連結等等)，您必須將要併入的項目明確新增致任何請求，否則請求不會自動產生。我們每個查詢串參數上用於追蹤的文件，都能在[此處](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html)找到。

若您檢查 amp-analytics 所創建的點擊，您會注意到每個請求中都有 Adobe 納入的 `vid` 查詢參數。我們根據內建的 AMP 功能設定 `vid`，以設定自訂的 Analytics 小型文字檔案 ID，命名為 `adobe_amp_id`。該 ID 獨立於其他 [!DNL Adobe Analytics] 於他處設定的任何 ID (如 `s_vi cookie`，並能於點擊所送至的任何報表套裝中創建新的訪客。

請注意以下警告。使用前述的 amp-analytics 標記時，訪客會獨立於您一般的追蹤，且由於 AMP 可以自任何內容傳遞網路載入，您在訪客所見 AMP 開啟的 CDN 上都會得到一位獨特訪客 (因此造成前述的訪客流量膨脹)。為了這個緣故，Adobe 建議，若您使用 `"adobeanalytics"` 範本來進行 `amp-analytics`，您可以將資料放進 AMP 指定的個別報表套裝。此外，[!DNL Experience Cloud] ID 服務 (先前稱為 *`visitor ID service`*) 並不支援此方式，因此若您的業務現在或將來需要額外的 [!DNL Experience Cloud] 整合，這種方式可能不適用於您的情形。

最後，也許也是最重要的一點，此 `amp-analytics` 解決方案要求您於 `vars` 區段中指定的追蹤伺服器符合您主要網站的追蹤伺服器，以便讓您現有的隱私權政策能執行。否則，您必須位 AMP 創建個別專用的隱私權政策。

## 使用有「adobeanalytics_nativeConfig」範本的 amp-analytics 標記。 {#section_3556B68304A4492991F439885727E9FF}

`"adobeanalytics_nativeConfig"` 標籤讓實施變得更輕鬆，因為這種標籤使用與您在一般網頁上使用的標籤方式相同。要完成這點，請將以下項目新增至您的 `amp-analytics` 標記:

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  
```

此方式透過新增到 `iframeMessage` 的特別查詢字串參數，將資料傳送到通用網頁。在此情形，請注意我們已新增 `ampdocUrl AMP` 變數，以及導向 `documentReferrer` 的 `pageURL`，並分別導向上述請求的 `iframeMessage`。您可以隨意命名這些額外的查詢字串參數，只要您的 [!DNL stats.html] 頁面 (如以下所示) 已設定，能從這些參數收集適當資料即可。

`"adobeanalytics_nativeConfig"` 範本也根據列於 amp-analytics 標記的 `extraUrlParams` 區段變數，新增查詢字串參數。在此情況下，您可以看見我們已指定 `pageName` 及 `v1` 參數，這兩者將用於 [!DNL stats.html] 頁面。

請注意，您一次只能使用一個 `amp-analytics` 範本，並且不能使用相同 AMP 上的 `"adobeanalytics"` 範本以及 `"adobeanalytics_nativeConfig"` 範本。若您試圖這麼做，您會在瀏覽器控制台上看到錯誤，且您會錯誤膨脹您的訪客計數。

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam("ref"); 
s.t(); 
</script> 
</body> 
</html> 
```

如上所示，您可以使用或連結至現有的 [!DNL VisitorAPI.js] 及 [!DNL AppMeasurement.js] (如範例)，或任何您現有的實施用途，再新增正確的設定參數。若要將正確數值擷取進正確變數，您可以使用我們提供的 `s.Util.getQueryParam` 函數來抽出您從 `iframeMessage` URL 及設定好的適當參數中傳入的數值，這也和您在典型網頁上擷取數值的方式並無不同。If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. 在此情形下，會將 `s.pageName` 設定為已傳入 `pageName` 查詢字串參數的數值。在此，頁面名稱會設定為 *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>鑒於 AMP 架構中對 iframe 有所限制，您的 [!DNL stats.html] 頁面應託管於 AMP 本身託管網域的獨立子網域。AMP 架構不允許來自與 AMP 本身存在網域相同之子網域的  iframe。舉例說明，若您的 AMP 託管於 [!DNL amp.example.com]，請務必將您的 [!DNL stats.html] 頁面託管於一獨立子網域，如 [!DNL ampmetrics.example.com] 或類似者。

由於該公用程式網頁已託管於您原始網站，故不須額外步驟支援您在所有 AMP 上的現有隱私政策。若使用者選擇不追蹤您的原始網站，使用者也可以選擇不追蹤您所有的 AMP，且不需額外步驟。使用此公用程式頁面，即表示 AMP 可支援 Adobe 的 [!DNL Experience Cloud] ID 服務，如此一來您就能將從 AMP 擷取的測量與其他 [!DNL Experience Cloud] 服務 (針對目標廣告則以 [!DNL Adobe Audience Manager] 為例) 整合在一起。

若您的組織尚未使用 [!DNL Experience Cloud] ID 服務，(或有類似 Adobe [!DNL Dynamic Tag Manager] 的標記管理軟體)，您可以藉由任意標記 [!DNL stats.html] 頁面來重複該步驟。請使用現有的實施作為參照點。與您標準的實施相較，唯一差異在於所有您想設定的變數都能從 `iframeMessage` URL 得到可用的資料點 (或從 [!DNL document.URL] 頁面內得到 [!DNL stats.html])。若您想使用任何特定 [AMP 變數](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) (如上所述)，如AMP 反向連結或 AMP 頁面 URL，請將這些變數納入 iframeMessage 物件，如上例所示。

此解決方案雖有彈性，但仍有警告事項。由於 `amp-analytics``iframeMessage` 本身的限制，其僅能於每個頁面載入一次。這表示您將無法連結追蹤或視訊追蹤與 `"adobeanalytics_nativeConfig"` 範本。此外，有些由我們 [!DNL AppMeasurement] 程式碼自動擷取出的 DOM 數值，例如`referrer` (這會影響搜尋引擎關鍵字報告、反向連結及反向連結類型報告，或可能包含行銷計畫追蹤代碼)，不論使用什麼`iframeMessage`可用[的 AMP 變數，這些數值都須以手動方式傳入 ](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)。變數如此一來，標準技術報告，如瀏覽器、裝置、螢幕大小或解析度，都應自動運作。

最後，由於 iframe 以獨立頁面載入，並在頁面上完全執行 JavaScript，該 AMP 並不如 AMP 標準預期的輕量。進一步說明，此並不影響頁面載入時間，(iframe 會於頁面載入完畢後載入)，但 CPU 及網路的工作量會略增，進而影響捲動頁面的流暢度。實務上，我們尚未發現較大的影響，但我們正與 Google 合作，設法減少此方式對使用者體驗

## 摘要 {#section_4D8ED26084F249738A5C2BC66B933A07}

若您需要點擊追蹤功能，且不介意正在您的網站以外將訪客以全新訪客計算數目，請使用 `"adobeanalytics"` 追蹤範本，並按照我們的建議將資料放進 *`separate report suite`*。若您需要 [!DNL Experience Cloud] ID 服務，不希望訪客或訪客流量膨脹，且不介意頁面載入僅啟動 Analytics，那麼推薦您使用 `"adobeanalytics_nativeConfig"` 解決方案。

Adobe Analytic 對於與 Google 及我們的發佈者合作興致勃勃，期待於行動網路將業界領先的分析功能帶給發佈者，提供超凡的高速使用者體驗。雖然這兩種解決方案目前已經上市，我們仍致力於建立最佳的長期解決方案，以回應客戶不斷改變的分析需求。

AMP 專案正快速演進且時常產生變更，所以請您經常於[此處](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)檢查範例的更新項目。我們於此說明的內容應足供您踏出第一步，但隨著我們進一步改善整合方式，以及採用 AMP 的發佈者人數增加，請期待我們將做出更多變更。

若您有問題或疑問，請聯繫您的 Adobe 顧問或客戶服務。

## 常見問題集 {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Is video tracking available for either the <code> "adobeanalytics" </code> or <code> "adobeanalytics_nativeConfig" </code> template? </p> </td> 
   <td colname="col2"> <p> 非常抱歉，目前尚未提供。AMP 標準支援僅觸發「可見」、「按一下」及「計時器」功能，且尚不對可用 amp-analytics 標記聆聽的視訊追蹤支援直接觸發器。Also, because the <code> "adobeanalytics_nativeConfig" </code> tag can only be loaded once, it is not compatible with video viewing which occurs after the AMP has loaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>你們在比較中提到<code> adobeanalytics_nativeConfig </code>「」範本的訪客數量膨脹較低。那是什麼意思? What would cause visitor inflation in either the <code> "adobeanalytics" </code> or the <code> "adobeanalytics_nativeConfig" </code> solution? </p> </td> 
   <td colname="col2"> <p>The <code> "adobeanalytics" </code> template does not allow Adobe Analytics to set a visitor identification cookie; this means all visits and visitors to your AMP page will be treated as a new and independent visit and visitor in your report suite. </p> <p>The <code> "adobeanalytics_nativeConfig" </code> template, however, allows the Adobe Analytics visitor identification cookie to be set in nearly all cases, except for new visitors using the Safari browser. 這表示，Safari的任何先前未造訪過發行者網站的訪客，在Adobe Analytics報告中都會被誇大。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否該為 AMP 使用個別報表套裝? </p> </td> 
   <td colname="col2"> <p>若您使用 adobeanalytics 範本，基於訪客或造訪數量膨脹的問題，我們建議您為 AMP 使用個別報表套裝。然而，我們也會從 amp-analytics 範本將 JavaScript 的版本設定為 AMP vX.X，以讓您可以在必要時分隔出合併報表套裝中的流量區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>什麼是 <span class="keyword">Experience Cloud</span> ID 服務? 我需要這項服務嗎? </p> </td> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/"  >Identity 服務 </a> (先前稱為<span class="term">訪客 ID 服務</span>) 可支援 <span class="keyword">Experience Cloud</span> 核心服務，並可在不同的 Adobe <span class="keyword"> Experience Cloud </span> 解決方案之間進行整合。若您的整合項目中有 <span class="keyword">Adobe Audience Manager</span> 或 <span class="keyword">Adobe Target</span>，您就很可能使用此服務。此服務為許多即將上市的 <span class="keyword">Adobe Analytics</span> 功能之基礎。若您現在或將來需要 ID 服務支援，建議您使用 <code> iframeMessage </code> 解決方案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For the <code> "adobeanalytics_nativeConfig" </code> template, where should I host my utility page? </p> </td> 
   <td colname="col2"> <p>AMP 標準並不允許 iframe 自 AMP 本身的網域與子網域載入。若是如此，建議您將公用程式網頁託管於您的主網站以外的個別子網域，特別是貴公司有自己計畫快取 AMP 的 CDN 時，更應如此。要設定最大相容性，請選擇一個子網域，如 <span class="filepath">ampmetrics.publisher.com</span>，此子網域須與 AMP 內容實際放置之處不同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>這與 <span class="keyword">Facebook 即時文章</span>不是很像嗎 ? 我該如何設定用 Facebook 即時文章功能設定 <span class="keyword">Adobe Analytics</span>? </p> </td> 
   <td colname="col2"> <p> Facebook 即時文章支援的解決方案與以上概述的 nativeConfig 解決方案相似。事實上，以上創建的 stats.html 頁面可以同時滿足您對 AMP 及 FIA 的需求。想取得更多 在 FIA 上實施追蹤功能的資訊，請參見<a href="/help/implement/js-implementation/analytics-facebook-instant-articles.md"  > Facebook 即時文章 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>


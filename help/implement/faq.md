---
description: 實作的相關常見問題，以及可提供更多資訊的連結。
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
title: Analytics 實作常見問題集
topic: Developer and implementation
uuid: 983d759a-c4f2-4021-84c8-0486dbb951b8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Analytics 實作常見問題集

實作的相關常見問題，以及可提供更多資訊的連結。

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>問題</b> </td> 
   <td> <b>回答</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>如何管理 Analytics 使用者和群組? </p> </td> 
   <td colname="col3"> <p>如需管理使用者和群組的相關資訊，請參閱 Adobe Experience Cloud 說明中的<a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html">使用者和產品管理</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>eVar有效期——為什麼eVar會被歸因為報表中的「無」? </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol">過期時間</span>能指定時段或事件，在發生此時段或事件後，eVar 值就會過期 (不再接收成功事件的評價)。如果成功事件發生在 eVar 過期後，「無」值會接收事件的評分 (沒有作用中的 eVar 值)。如果您選取事件作為過期值，則變數在事件發生時才會過期。如果事件未發生，變數永遠不會過期。<a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>自訂事件可見性 - 為何自訂事件不會出現在報表功能表中? </p> </td> 
   <td colname="col3"> <p>在「可見性」欄中，您可以在功能表、量度選擇器、計算量度產生器及區段產生器中隱藏標準 (內建) 量度、自訂事件及內建事件。此設定不會影響該量度或事件的資料收集作業，只會影響其使用者介面的可見性。<a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>時間戳記 - 變更時間戳記設定前，需要考量哪些事項? </p> </td> 
   <td colname="col3"> <p>使用可選時間戳記功能，您可以結合非時間戳記資料與時間戳記資料，而不會導致資料遺失。收集自行動裝置的附時間戳記離線資料可與來自網頁的即時非時間戳記資料相結合，或與使用用戶端時間戳記呼叫的平台資料相整合。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>訪客 ID - 訪客 ID 寬限期如何運作及啟動? </p> </td> 
   <td colname="col3"> <p>如果您有多個 JavaScript 檔案會傳送資料至相同的報表套裝，或是您在網站上使用其他技術 (例如 Flash 視訊測量)，建議您設定寬限期。<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>訪客 ID - Experience Cloud 訪客 ID 與 Analytics 訪客 ID 有何不同? </p> </td> 
   <td colname="col3"> <p>Identity 服務會指派不重複的永久性識別碼給所有網站訪客。有了此 ID，便可在 Experience Cloud 的其他解決方案之間共用訪客及其資料。此外，此 ID 也能取代或與解決方案專用的 ID 共同運作，例如 Analytics 訪客 ID。<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>訪客 ID - 若 Cookie 遭到封鎖，如何設定訪客 ID? </p> </td> 
   <td colname="col3"> <p>在標準 s_vi Cookie 無法使用時，將會以隨機產生的唯一 ID 在網站的網域上建立備援 Cookie。此 Cookie (名為 s_fid) 會設定 2 年的有效期，且會作為後續的備援身分識別方法。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dynamic Tag Management - 為何我的 DTM 規則沒有觸發? </p> </td> 
   <td colname="col3"> <p>如果您的事件型規則沒有受到觸發，可能是因為選擇器或規則條件發生問題。請在網站上找到發生所需事件動作的元素，按一下滑鼠右鍵然後選取「檢查元素」。在開啟的方塊中檢查醒目顯示的指令檔，確定您已鎖定正確的元素作為目標。<a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>如何實作心率視訊追蹤? </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/">此區段</a>包含下載視訊心率 SDK 的相關說明，以及您平台的開發者指南。請確保您也下載開發者指南，內容有對於視訊心率的特定實作指示，您在下載 SDK 時，該指南會包含於文件資料夾中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>如何將 Cookie 新增至正確的子網域? </p> </td> 
   <td colname="col3"> <span class="varname">cookieDomainPeriods</span> 變數會判斷頁面 URL 網域中所含的句號數，以判定 Analytics Cookie s_cc 和 s_sq 設定所在的網域。有些外掛程式也會使用此變數來判斷設定外掛程式 Cookie 所需的正確網域。請參閱 [設定變數](/help/implement/js-implementation/c-variables/configuration-variables.md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>追蹤伺服器 - 如何正確填充我的追蹤伺服器? </p> </td> 
   <td colname="col3"> <p>您在設定傳送資料給 Adobe Analytics 伺服器的實作時，必須傳送至正確的位置。若有錯誤，將導致訪客計數膨脹或資料遺失。<a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html"> [更多...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>效能 - 無法載入外部 Adobe JavaScript (由於網際網路連線、Proxy、防火牆或 Adobe 服務中斷等原因) 是否會影響效能? </p> </td> 
   <td colname="col3"> <p>不可以。JavaScript 檔案並非由 Adobe 伺服器託管，所以 Adobe 中斷不會影響 JavaScript 執行。如果採用 Dynamic Tag Management，則 JavaScript 檔案是由 Akamai 託管，或位在客戶決定的伺服器位置。 </p> <p>請參閱 <i>Dynamic Tag Management 會降低我網站的效能嗎? </i> (位於 <a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html">Dynamic Tag Management 常見問題集 </a>)。 </p> <p>此外，如果您不想依賴 Akamai 的 CDN，也可以主控自己的核心 Dynamic Tag Management 檔案。請參閱<a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html">內嵌代碼和託管選項</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>效能 - 載入外部 Adobe JavaScript 會導致效能降低嗎? </p> </td> 
   <td colname="col3"> <p> JavaScript 檔案初始載入後會置於訪客瀏覽器的快取中，通常一個工作階段不會下載超過一次。此檔案即使用於網站上的每個頁面，也不會下載至每個頁面上。大部分網站上，使用者在每個工作階段中會檢視多個頁面，所以將多次使用的 JavaScript 傳輸至此檔案可以減少整體資料下載量。 </p> <p> 以 JavaScript 壓縮 AppMeasurement: 若您對 Adobe JavaScript 用戶端的頁面寬度 (大小) 有所顧慮，Adobe 建議您考慮使用 GZIP 來壓縮檔案。所有主要瀏覽器都可支援 GZIP，且在壓縮及解壓縮核心 <span class="filepath">s_code.js</span> JavaScript 檔案的效能上，GZIP 都優於 JavaScript 壓縮。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>效能 - 從瀏覽器傳送資料給 Adobe 服務會降低效能嗎? </p> </td> 
   <td colname="col3"> <p> Adobe JavaScript 檔案會在 HTML 頁面內部建立影像物件，接著瀏覽器再向 Adobe 伺服器請求該影像物件。如果 Adobe 伺服器緩慢或無反應，處理該請求的執行緒會延遲，直到傳回影像或逾時。因為瀏覽器使用多個執行緒來處理影像，Adobe 中斷對頁面載入時間的影響極小，最多只會佔用一個執行緒，而其他執行緒仍持續運作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>效能 - 來自 Adobe 的 JavaScript 事件會影響系統行為或功能嗎? </p> </td> 
   <td colname="col3"> <p>不可以。請參閱前面的效能解答。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 我可以根據自己的定義條件，變更收集的資料嗎? </td> 
   <td colname="col3"> 使用處理規則可簡化資料收集作業，並在資料傳送至報表後管理內容。<a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> s_code 檔案的最新版本是什麼? </td> 
   <td> This section contains a release history for <code>AppMeasurement</code> libraries across web and mobile platforms. 每個程式庫的最新版本可從「Reports &amp; Analytics &gt; 管理工具 &gt; 代碼管理器」下載。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/c_release_notes_javascript.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 如何偵錯 s_code 檔案? </td> 
   <td> Adobe Debugger (舊稱為 DigitalPulse Debugger) 是 Adobe 提供的免費工具，可以在任何指定頁面上檢視從您網站收集到的資料。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 如何追蹤不同的連結類型? </td> 
   <td> 系統會根據「JavaScript 適用的 AppMeasurement」檔案所設定的參數，自動追蹤檔案下載和退出連結。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 如何追蹤視訊? </td> 
   <td> JavaScript 可以用來追蹤多種播放器。若要使用 JavaScript 進行追蹤，您可將程式碼新增至包含播放器的網頁，並使用事件處理程式追蹤播放器。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 如何追蹤行動應用程式? </td> 
   <td> 可以在 Adobe Mobile Services 中產生具備獨特追蹤代碼的贏取連結。當使用者按一下產生的連結，從 Apple App Store 下載並執行應用程式後，SDK 就會自動收集並傳送贏取資料至 Adobe Mobile Services。<a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/acquisition.html"> iOS</a> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/acquisition.html">Android </a> </td> 
  </tr> 
  <tr> 
   <td> 如何實作視訊追蹤? </td> 
   <td> 您可建立相關功能，並將功能附加到視訊播放器事件的處理常式，藉此追蹤媒體撥放器。如此一來，您就可以在適當時機呼叫 Media.open、Media.play、Media.stop 和 Media.close。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js_events.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 如何設定第一方 Cookie? </td> 
   <td> Analytics 會使用 Cookie，針對未跨影像請求與瀏覽器作業存留的變數和元件提供相關資訊。這些無害的 Cookie 源自 Adobe 所經營的網域，稱為第三方 Cookie。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 如何取得 SSL 憑證? </td> 
   <td> 確定您的網站是否使用 https:// 通訊協定。如果是，則必須請求 CSR 並購買 SSL 憑證。注意: 如果您沒有任何安全的頁面或內容，則不需要 SSL 憑證。如果您的網站僅使用 https:// 通訊協定，可跳過這整個步驟。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 哪裡可以找到憑證過期通知的相關資訊? </td> 
   <td> SSL 憑證每年會到期一次，這表示每當到期時，Adobe 就會要求要有更新的憑證請求。FPC 專員會在到期時發出警告，但建議您主動監控到期時間，並向 Adobe 提供此更新的憑證。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_renewals.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 什麼是外掛程式? </td> 
   <td> 「JavaScript 適用的 AppMeasurement」外掛程式是可執行數種進階功能的程式或函數。這些外掛程式可擴充 JavaScript 檔案的功能，讓您獲得更多在基本實作中無法使用的功能。Adobe 在進階解決方案中另外提供了許多外掛程式。若您想要使用 JavaScript 擷取資料，但不確定如何進行，請與客戶經理連絡。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/impl_plugins.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 資料插入 API 的相關資訊? </td> 
   <td> Adobe 提供多種將資料傳入 Analytics 的方式。<a href="https://marketing.adobe.com/resources/help/en_US/reference/usecase_sending_data_to_sc.html"> [更多...] </a> </td> 
  </tr> 
  <tr> 
   <td> 500 錯誤是什麼? </td> 
   <td> 造成「500 查詢錯誤」狀態之內部伺服器錯誤的相關資訊。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageType.html">請參閱 pageType 變數 </a> </td> 
  </tr> 
 </tbody> 
</table>

| 問題 | 回答 |
|---|---|
| 如何管理 Analytics 使用者和群組? | 如需有關管理使用者和群組的詳細資訊，請 [參閱Adobe Experience cloud核心服務說明中的](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) 「管理Experience cloud使用者和產品」。 |
| eVar有效期——為什麼eVar會被歸因為報表中的「無」? | `Expire After` 會指定時段或事件，經過此時段或事件後，eVar 值就會過期 (不再接收成功事件的評分)。如果成功事件發生在 eVar 過期後，「無」值會接收事件的評分 (沒有作用中的 eVar 值)。如果您選取事件作為過期值，則變數在事件發生時才會過期。如果事件未發生，變數永遠不會過期。[[更多...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| 自訂事件可見性 - 為何自訂事件不會出現在報表功能表中? | 在「可見性」欄中，您可以在功能表、量度選擇器、計算量度產生器及區段產生器中隱藏標準 (內建) 量度、自訂事件及內建事件。此設定不會影響該量度或事件的資料收集作業，只會影響其使用者介面的可見性。[[更多...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/metric-visibility.html) |
| 時間戳記 - 變更時間戳記設定前，需要考量哪些事項? | 使用可選時間戳記功能，您可以結合非時間戳記資料與時間戳記資料，而不會導致資料遺失。收集自行動裝置的附時間戳記離線資料可與來自網頁的即時非時間戳記資料相結合，或與使用用戶端時間戳記呼叫的平台資料相整合。[[更多...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/timestamps-overview.html) |
| 訪客 ID - 訪客 ID 寬限期如何運作及啟動? | 如果您有多個 JavaScript 檔案會傳送資料至相同的報表套裝，或是您在網站上使用其他技術 (例如 Flash 視訊測量)，建議您設定寬限期。[更多...](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html) |
| 訪客 ID - Experience Cloud 訪客 ID 與 Analytics 訪客 ID 有何不同? | Identity 服務會指派不重複的永久性識別碼給所有網站訪客。有了此 ID，便可在 Experience Cloud 的其他解決方案之間共用訪客及其資料。此外，此 ID 也能取代或與解決方案專用的 ID 共同運作，例如 Analytics 訪客 ID。[更多...](https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html) |
| 訪客 ID - 若 Cookie 遭到封鎖，如何設定訪客 ID? | 在標準 s_vi Cookie 無法使用時，將會以隨機產生的唯一 ID 在網站的網域上建立備援 Cookie。此 Cookie (名為 s_fid) 會設定 2 年的有效期，且會作為後續的備援身分識別方法。[更多...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/unique-visitors/visid-fallback.html) |
| Dynamic Tag Management - 為何我的 DTM 規則沒有觸發? | 如果您的事件型規則沒有受到觸發，可能是因為選擇器或規則條件發生問題。請在網站上找到發生所需事件動作的元素，按一下滑鼠右鍵然後選取「檢查元素」。在開啟的方塊中檢查醒目顯示的指令檔，確定您已鎖定正確的元素作為目標。[更多...](https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html) |
| 如何實作心率視訊追蹤? | [此區段](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html)包含下載視訊心率 SDK 的相關說明，以及您平台的開發者指南。請確保您也下載開發者指南，內容有對於視訊心率的特定實作指示，您在下載 SDK 時，該指南會包含於文件資料夾中。 |
| 如何將 Cookie 新增至正確的子網域? | cookieDomainPeriods 變數會判斷頁面 URL 網域中所含的句號數，以判定 Analytics Cookie s_cc 和 s_sq 設定所在的網域。有些外掛程式也會使用此變數來判斷設定外掛程式 Cookie 所需的正確網域。See [Configuration Variables](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/configuration-variables.html) |
| 追蹤伺服器 - 如何正確填充我的追蹤伺服器? | 您在設定傳送資料給 Adobe Analytics 伺服器的實作時，必須傳送至正確的位置。若有錯誤，將導致訪客計數膨脹或資料遺失。[更多...](https://helpx.adobe.com/analytics/kb/determining-data-center.html) |
| 效能 - 無法載入外部 Adobe JavaScript (由於網際網路連線、Proxy、防火牆或 Adobe 服務中斷等原因) 是否會影響效能? | 不可以。JavaScript 檔案並非由 Adobe 伺服器託管，所以 Adobe 中斷不會影響 JavaScript 執行。 |
| 效能 - 載入外部 Adobe JavaScript 會導致效能降低嗎? | JavaScript 檔案初始載入後會置於訪客瀏覽器的快取中，通常一個工作階段不會下載超過一次。此檔案即使用於網站上的每個頁面，也不會下載至每個頁面上。大部分網站上，使用者在每個工作階段中會檢視多個頁面，所以將多次使用的 JavaScript 傳輸至此檔案可以減少整體資料下載量。<br>以 JavaScript 壓縮 AppMeasurement: 若您對 Adobe JavaScript 用戶端的頁面寬度 (大小) 有所顧慮，Adobe 建議您考慮使用 GZIP 來壓縮檔案。所有主要瀏覽器都可支援 GZIP，且在壓縮及解壓縮核心 `s_code.js` JavaScript 檔案的效能上，GZIP 都優於 JavaScript 壓縮。 |
| 效能 - 從瀏覽器傳送資料給 Adobe 服務會降低效能嗎? | Adobe JavaScript 檔案會在 HTML 頁面內部建立影像物件，接著瀏覽器再向 Adobe 伺服器請求該影像物件。如果 Adobe 伺服器緩慢或無反應，處理該請求的執行緒會延遲，直到傳回影像或逾時。因為瀏覽器使用多個執行緒來處理影像，Adobe 中斷對頁面載入時間的影響極小，最多只會佔用一個執行緒，而其他執行緒仍持續運作。 |
| 效能 - 來自 Adobe 的 JavaScript 事件會影響系統行為或功能嗎? | 不可以。請參閱前面的效能解答。 |
| 我可以根據自己的定義條件，變更收集的資料嗎? | 使用處理規則可簡化資料收集作業，並在資料傳送至報表後管理內容。([更多...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| s_code 檔案的最新版本是什麼? | 本區段包含 Web 及行動平台上 AppMeasurement 程式庫的版本記錄。每個程式庫的最新版本可從「Analytics &gt; 管理員 &gt; 代碼管理器」下載。[更多...](/help/implement/appmeasurement-release-notes/c-release-notes-mjs.md) |
| 如何偵錯 s_code 檔案? | Experience Cloud Debugger 是 Adobe 提供的免費工具，可以在任何指定頁面上檢視從您網站收集到的資料。[更多...](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) |
| 如何追蹤不同的連結類型? | 系統會根據「JavaScript 適用的 AppMeasurement」檔案所設定的參數，自動追蹤檔案下載和退出連結。[更多...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/function-tl.html) |
| 如何追蹤視訊? | JavaScript 可以用來追蹤多種播放器。若要使用 JavaScript 進行追蹤，您可將程式碼新增至包含播放器的網頁，並使用事件處理程式追蹤播放器。[更多...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| 如何追蹤行動應用程式? | 可以在 Adobe Mobile Services 中產生具備獨特追蹤代碼的贏取連結。當使用者按一下產生的連結，從 Apple App Store 下載並執行應用程式後，SDK 就會自動收集並傳送贏取資料至 Adobe Mobile Services。[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)、 [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html) |
| 如何實作視訊追蹤? | 您可建立相關功能，並將功能附加到視訊播放器事件的處理常式，藉此追蹤媒體撥放器。如此一來，您就可以在適當時機呼叫 Media.open、Media.play、Media.stop 和 Media.close。[更多...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| 如何設定第一方 Cookie? | Analytics 會使用 Cookie，針對未跨影像請求與瀏覽器作業存留的變數和元件提供相關資訊。這些無害的 Cookie 源自 Adobe 所經營的網域，稱為第三方 Cookie。[更多...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| 如何取得 SSL 憑證? | 確定您的網站是否使用 `https://` 通訊協定。如果是，則必須請求 CSR 並購買 SSL 憑證。注意: 如果您沒有任何安全的頁面或內容，則不需要 SSL 憑證。如果您的網站僅使用 `https://` 通訊協定，則可以跳過這整個步驟。[更多...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| 哪裡可以找到憑證過期通知的相關資訊? | SSL 憑證每年會到期一次，這表示每當到期時，Adobe 就會要求要有更新的憑證請求。FPC 專員會在到期時發出警告，但建議您主動監控到期時間，並向 Adobe 提供此更新的憑證。[更多...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) |
| 什麼是外掛程式? | 「JavaScript 適用的 AppMeasurement」外掛程式是可執行數種進階功能的程式或函數。這些外掛程式可擴充 JavaScript 檔案的功能，讓您獲得更多在基本實作中無法使用的功能。Adobe 在進階解決方案中另外提供了許多外掛程式。若您想要使用 JavaScript 擷取資料，但不確定如何進行，請與客戶經理連絡。[更多...](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) |
| 如何取得資料插入 API 的相關資訊? | Adobe 提供多種將資料傳入 Analytics 的方式。[更多...](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
| 500 錯誤是什麼? | 有關導致「500查詢錯誤」狀態的內部伺服器錯誤的資訊，請參閱 [pageType變數](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables.html#concept_F67870238EF74491B5D3909A33CDB985)。 |

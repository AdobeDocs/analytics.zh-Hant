---
description: Adobe 可使用 Cookie 來追蹤獨特的瀏覽器/裝置。
keywords: Analytics Implementation
subtopic: Visitors
title: 識別不重複訪客
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 識別不重複訪客

Adobe 可使用 Cookie 來追蹤獨特的瀏覽器/裝置。

## Analytics 訪客 ID 順序 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics提供數種識別訪客的機制。 下表列出訪客在Analytics中可識別的不同方式（依偏好順序）:

| 使用的訂單 | 查詢參數（收集方法） | 在 |
|---|---|---|
| 1 | vid (s.visitorID) | 設定 s.visitorID 時 |
| 2 | aid (s_vi Cookie) | 在您部署訪客 ID 服務之前訪客已有 s_vi Cookie，或是您有設定訪客 ID 的寬限期。 |
| 3 | mid (Experience Cloud 訪客 ID 服務所設定的 AMCV_ Cookie) | 訪客的瀏覽器接受 Cookie (第一方) |
| 4 | fid (備援 Cookie) | 訪客的瀏覽器接受 Cookie (第一方) |
| 5 | IP 位址、使用者代理、閘道 IP 位址 | 訪客的瀏覽器不接受 Cookie |

在許多情況下，您可能會在呼叫中看到2或3個不同的ID，但Analytics會使用上表中第一個顯示的ID做為正式訪客ID。 例如，如果您設定自訂訪客 ID (內含於 &quot;vid&quot; 查詢參數中)，則在同一個點擊可能存在其他 ID 時，將優先使用該自訂訪客 ID。

>[!NOTE]每個 Analytics 訪客 ID 都與 Adobe 伺服器上的訪客資料相關聯。無論訪客 ID Cookie 過期與否，訪客閒置最少 13 個月就會刪除其訪客資料。

## 自訂訪客 ID

您可以實施自訂方法，設定 s.visitorID 變數以識別訪客。

自訂訪客ID可用於您有獨特方式識別訪客的網站。 例如，當使用者使用使用者名稱和密碼登入網站時，會產生ID。

如果您有能力衍生和管理使 [!UICONTROL visitor IDs] 用者，則可使用下列方法來設定ID:

| 方法 | 說明 |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) 變數 | 如果瀏覽器上使用JavaScript，或您正在使用任何其他AppMeasurement程式庫，則可以在資料收集變數中設定訪客ID。 |
| 影像要求上的查詢字串參數 | 這可讓您透過硬式 [!UICONTROL visitor ID] 編碼影像要求 [!UICONTROL vid query string] 上的參數，將影像傳遞給Adobe。 |
| 資料插入 API | 在使用無線通訊協定，沒有接受 JavaScript 的裝置上，您可以從您的伺器將包含 `<visitorid/>` XML 元素的 XML 貼文傳送至 Adobe 收集伺服器。 |
| URL重寫和VISTA | 有些部署架構支援在無法設定Cookie時，使用URL重寫來維護工作階段狀態。 在這種情況下，Adobe 工程服務可實施 [!DNL VISTA] 規則以在頁面的 URL 中尋找工作階段值，並在格式化後將其放入 [!UICONTROL visid] 值中。 |
>[!CAUTION]
>**自訂訪客 ID 的精細/獨特程度必須足夠&#x200B;**: 無效的自訂訪客 ID 實施會導致不正確的資料和不良的報表效能。如果自訂訪客 ID 的獨特或精細程度不足，或誤設為字串「NULL」或「0」等常見預設值，則 Adobe Analytics 會將來自許多不同訪客的點擊視為單一訪客。此情況會導致不正確的資料，訪客計數會太低，且該訪客的區段無法正常運作。精細程度不足的自訂訪客 ID 也會讓資料無法正確分散到 Analytics 報表叢集中的各個節點。在此情況下，一個節點會變成超載，而無法及時地處理報表要求。最後，該報表套裝的所有報表作業都會失敗。<br>實作方式不佳的自訂訪客 ID 可能不會立即影響報表效能，因為 Analytics 通常可處理多個月份的不對稱資料，但一段時間過後，這類自訂訪客 ID 值可能會變得有問題，導致 Analytics 必須停用受影響報表套裝的處理作業。</br><br>實作者應按照相關準則，確保計入的單一自訂訪客 ID 值絕不超過報表套裝流量的 1%。雖然此 1% 準則對大多數的報表套裝來說已經足夠，但若為非常大型的報表套裝，可能導致報表效能受到影響的實際上限或許低於 1%。</br>

## Analytics 訪客 ID

當使用者瀏覽您的網站時，Adobe網站伺服器會將永久性Cookie加入瀏覽器的HTTP回應中，以設定它。 此Cookie是在指定的資料收集網域上設定。

當請求傳送至 Adobe 資料收集伺服器時，會檢查標題中是否有訪客 ID Cookie `s_vi`)。如果請求中有此 Cookie，便會用來識別訪客。如果Cookie不在請求中，伺服器會產生唯一訪客ID，在HTTP回應標題中將其設為Cookie，並隨請求傳回。 Cookie會儲存在瀏覽器中，並在後續造訪網站時傳回至資料收集伺服器，讓訪客在造訪時識別。

### 協力廠商Cookie和CNAME記錄 {#section_61BA46E131004BB2B75929C1E1C93139}

有些瀏覽器 (例如 Apple Safari) 不再從下列情況的網域儲存 HTTP 標題中設定的 Cookie: 不符合目前網站的網域 (這是協力廠商上下文中使用的 Cookie，或是協力廠商 Cookie)。例如，如果您位於 `mysite.com` 而您的資料收集伺服器是 `mysite.omtrdc.net`，則瀏覽器可能會拒絕從 `mysite.omtrdc.net` HTTP 標題中傳回的 Cookie。

為了避免此問題，許多客戶在進行[第一方 Cookie 實施](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)時，會為其資料收集伺服器實施 CNAME 記錄。如果已設定 CNAME 記錄將客戶網域的主機名稱對應至資料收集伺服器 (例如，將 `metrics.mysite.com` 對應至 `mysite.omtrdc.net`)，則資料收集網域現在符合網站的網域，因此可以儲存訪客 ID Cookie。這會增加訪客ID Cookie儲存的可能性，但會造成一些額外負荷，因為您需要設定CNAME記錄並維護資料收集伺服器的SSL憑證。

### 行動裝置上的Cookie {#section_7D05AE259E024F73A95C48BD1E419851}

使用 Cookie 追蹤行動裝置時，您可使用一些設定來修改測量的發生方式。Cookie 預設期限為 5 年，但您可使用 CL 查詢參數變數 (`s.cookieLifetime`) 來變更此預設值。若要設定 cname 實施的 Cookie 位置，請使用 CDP 查詢字串 `s.cookieDomainPeriods`。如果未指定值，則預設為2。 預設位置為domain.com。 若為未使用CNAME的實作，訪客ID Cookie位於207.net網域。

## Identity 服務

The Identity Service replaces the legacy Analytics visitor ID mechanism, and is required by [!UICONTROL Heartbeat] video measurement, Analytics for Target, and future Experience Cloud core services and integrations.

如需此服務的產品文件 ，請參閱 [Identity Service](https://marketing.adobe.com/resources/help/zh_TW/mcvid/)。

## 識別行動裝置

大部分行動裝置接受瀏覽器Cookie。 不過，當裝置不接受Cookie時，會使用其他方法來唯一識別無線裝置。

Adobe 已找出數個可唯一識別大多數行動裝置的 HTTP 訂閱者 OD 標題。這些標題通常包括裝置電話號碼（或號碼的雜湊版本）或其他識別碼。 目前大部份的裝置都有一個或多個可唯一識別裝置的標題，而所有Adobe資料收集伺服器都會自動使用這些標題來取代訪客ID。

In a typical image request, a &#39;1&#39; in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). 不過，如果根據HTTP標題將裝置辨識為行動裝置，則會傳遞&#39;5&#39;來取代&#39;1&#39;，這表示應傳回wbmp格式影像，並且應使用我們已辨識的無線標題清單（非Cookie）來識別裝置。

下表列出根據路徑中的傳回影像類型值（&#39;1&#39;或&#39;5&#39;）所使用之ID方法的順序：

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> ID方法順序 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>預設: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">自訂訪客 ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">訂閱者ID標題 </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IP位址——使用者代理——閘道IP位址 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>已將裝置識別為無線裝置，或已在影像請求中手動傳送 <code> /5/</code>: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">自訂訪客 ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">訂閱者ID標題 </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IP位址——使用者代理——閘道IP位址 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

您也可以在手動影像要求中傳遞&#39;1&#39;或&#39;5&#39;，但請注意，這些代碼是互斥的，因此，一律傳遞&#39;5&#39;並不會在支援Cookie時使用它。 您可以結合自己的機制來判斷裝置是否支援Cookie，若支援，請在影像中傳遞&#39;1&#39;，而非&#39;5&#39;。 此情況的正確性改進僅限於支援Cookie的行動裝置數目。

### 訂閱者ID標題 {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

由於Cookie刪除、Cookie接受問題和閘道Cookie管理問題，訂閱者ID方法通常比Cookie更可靠，以用於使用者識別。

您可以借由將訪客新增至您行動訪客所使用電信業者的白名單，改善識別訪客的變更。 若要存取電信業者的訪客ID，請連絡電信業者，將您的網域新增至其白名單。 如果您位於電信業者的白名單中，您也可以存取訂閱者ID標題，否則您將無法存取。

以下標題清單用於標識無線設備。 處理標題的演算法是

1. 擷取HTTP標題鍵（標題的名稱，例如&quot;X-Up-Calling-Line-ID&quot;）
1. 修剪所有非字母（A-Z和a-z）字元
1. 將標題鍵轉換為小寫
1. 將索引鍵結尾與下表中的索引鍵比較，以尋找相符項目：

| Header | 類型 | 範例 |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID:8613802423312 |
| subno | ID | x-up-subno:swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID:eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid:a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid:595961714786 |
| deviceid | ID | rim-device-id:200522ae |
| forwardedfor | ID或IP位址 | X-Forwarded-For:127.0.0.1 |
| msisdn | ID或IP位址 | X-Wap-msisdn:8032618185 |
| clientip | IP 位址 | Client-ip:10.9.41.2 |
| wapipaddr | IP 位址 | X-WAPIPADDR:10.48.213.162 |
| huaweinasip | IP 位址 | x-huawei-NASIP:211.139.172.70 |
| userip | IP 位址 | 用戶IP:70.214.81.241 |
| ipaddress | IP 位址 | X-Nokia-ipaddress:212.97.227.125 |
| subscriberinfo | IP 位址 | X-SUBSCRIBER-INFO:IP=10.103.132.128 |

例如，&quot;callinglineid&quot;會比對&quot;X-Up-Calling-Line-ID&quot;和&quot;nokia-callinglineid&quot;。 標題類型會告訴我們標題中的預期項目。 標題優先順序列於此處（如果有&quot;callinglineid&quot;標題，則使用它，而非&quot;subno&quot;）。

You can use [Dynamic Variables](../implement/vars/page-vars/dynamic-variables.md) to extract specific values from a header.

## 備援 ID 方法

如果其他訪客 ID 方法失敗，則 Adobe 會設定一個回呼 Cookie，或使用 IP 位址與使用者代理程式的組合來識別訪客。

### 備援訪客身分識別方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

JavaScript 1.x 及 JavaScript H.25.3 適用的 AppMeasurement (於 2013 年 1 月發行) 包含新的備援訪客身分識別方法，如有訪客的瀏覽器會封鎖 Adobe 資料收集伺服器所設定的 Cookie (名為 `s_vi`)，此項目可用於解決問題。過去在無法設定 Cookie 時，在資料收集期間會使用 IP 位址和使用者代理字串的組合來識別訪客。

透過這項更新，在標準 `s_vi` Cookie 無法使用時，將會以隨機產生的唯一 ID 在網站的網域上建立備援 Cookie。此 Cookie (名為 `s_fid`) 會設定 2 年的有效期，且會作為後續的備援身份識別方法。在無法設定主要 Cookie (`AMCV_` 或 `s_vi`) 的情況下，此變更應該導致瀏覽正確性和瀏覽數增加。

瀏覽總計會包含所有以 `s_vi` Cookie 識別，或使用備援方法識別的訪客數。

### IP 位址、使用者代理、閘道 IP 位址 {#section_104819D74C594ECE879144FCC5DEF4BF}

。如果無法設定 `AMCV_` 或 `s_vi` 和 `s_fid` Cookie，將會使用 IP 位址和使用者代理的組合來識別訪客。

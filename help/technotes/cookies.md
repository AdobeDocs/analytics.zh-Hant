---
title: Adobe Analytics和瀏覽器Cookie
description: 瞭解Adobe Analytics如何處理瀏覽器的Cookie。
translation-type: tm+mt
source-git-commit: 3566960f546d847ed4f6ca8ecbb9c759460f4fb0

---


# Adobe Analytics和瀏覽器Cookie

為支援跨屬性和解決方案的永續使用者識別，Adobe Analytics會回應瀏覽器處理Cookie的方式變更。 下列常見問答集提供如何隨著瀏覽器Cookie變更而保留永久性訪客識別的資訊。

## 瀏覽器如何改變處理Cookie的方式？

一般而言，大部份的瀏覽器在存放協力廠商Cookie的方式上都變得更嚴格。 如果瀏覽器刪除或拒絕Cookie，這會影響追蹤。 此外，Safari瀏覽器也會針對某些第一方Cookie設定一些限制。

下列清單會根據瀏覽器顯示一些最近的變更：

* Chrome:從Chrome 80開始，屬 `SameSite` 性的處理方式不同，以管理協力廠商Cookie或跨網站請求。 最終，Chrome開發人員正在尋找完全取 [代協力廠商Cookie的方式](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1) 。

* Firefox和Edge:產品公告指出其瀏覽器的後續版本將遵循與Chrome 80中相同的變更。

* Safari: With [Safari 12.1](https://webkit.org/blog/category/privacy/), first party persistent cookies set through the document.cookie API, often known as “client-side” cookies, have their expiration capped at seven days.

## 協力廠商Cookie和第一方Cookie之間有何差異？

### 第一方 Cookie

第一方Cookie是由客戶網站（網域特定）建立，當使用者造訪客戶網站時，會儲存在用戶端瀏覽器中。 所有瀏覽器通常都接受第一方Cookie。 在第一方Cookie Analytics實作中，當主機名稱與網域使用 [CNAME協調時，訪客ID cookie會建立在Adobe節點上](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html)。 然後瀏覽器會在第一方內容中接受Cookie。 如需詳細資訊，請 [參閱關於第一方Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html)。

### 協力廠商Cookie

協力廠商Cookie不是由使用者造訪的網站所建立。 雖然瀏覽器目前對所有第三方Cookie的處理方式相同，並據以儲存，但第三方Cookie本身的行為方式可能不同。 透過客戶的Analytics協力廠商Cookie實作，客戶僅會呼叫Adobe，而不會呼叫未知或可疑的協力廠商網域。 這是目前實作Analytics以進行安全(HTTPS)且使用永久性識別碼進行可靠追蹤的方法。 此方法是透過設定AppMeasurement.js檔案來實作。 如需詳細資訊，請 [參閱Cookie和Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html)。

![Cookie比較](assets/cookies2.png)

## 瀏覽器目前如何儲存和管理Analytics Cookie?

根據實作，Analytics cookie會儲存如下：

### 協力廠商Cookie實作

瀏覽器目前會將Adobe [demdex.net](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/demdex-calls.html) ID儲存為協力廠商Cookie。 此Cookie可跨網域提供永續性識別碼，並允許安全(https)內容。

### 第一方Cookie實作

透過設定CNAME，您的使用者可以在其瀏覽器的第一方Cookie內容中收到Adobe Cookie。 如果協力廠商Cookie實作對您的使用者而言並非最佳，則此選項可能是可行的。

## 什麼是SameSite cookie屬性，它對Analytics有何影響？

隨著Chrome 80瀏覽器以及Firefox和Edge瀏覽器的相繼版本的發行，SameSite cookie屬性會針對三個不同值執行規格，以控制跨網站請求的行為，如下所示：

* `None`:此設定可啟用跨網站存取，並可在協力廠商內容中傳遞Cookie。 若要指定此屬性，您也必須指定， `Secure` 且所有瀏覽器要求都必須遵循HTTPS。 例如，在設定Cookie時，您會依下列方式配對屬性的值： `Set-Cookie: example_session=test12; SameSite=None; Secure`。 如果未正確標示，則較新的瀏覽器將無法使用Cookie，並將遭拒。

* `Lax`:允許跨網站請求僅以同一網站Cookie傳送，適用於具有安全(唯讀 *，如*`GET`)HTTP方法的頂層導覽。

* `Strict`:不會針對任何第三方網站要求傳送同一網站Cookie。 只有當Cookie的網站與URL列中的網站相符時，才會傳送Cookie。

這些瀏覽器版本的預設行為是將未指定屬性的Cookie `SameSite` 視為 `SameSite=Lax`。

## Adobe Analytics如何回應這些變更？

所有Adobe cookie更新都會透過Adobe伺服器處理，而Adobe已更新其邊緣伺服器，以設定適當的Cookie屬性。 Adobe已發佈伺服器端更新，以使用適當屬性來設定其第三方Cookie。 您的網站不需要JavaScript更新。

當使用者造訪使用Cookie的任何網站時，Adobe Edge伺服器會自動進行此項升級。 對於大部分的Adobe產品，Cookie會在Chrome 80發行時有適當的標幟。 但Adobe Analytics實作中，使用協力廠商資料收集且不使用Experience Cloud Identity Service(ECID)的情況除外。 這些客戶可能會遇到新訪客的小幅度臨時增加，否則這些訪客會被標籤為舊訪客。

若是Google在設為時已識別為錯誤處 `SameSite` 理Cookie的 `None`瀏 `SameSite` 覽器，則會保留未設定。

下表摘要了Analytics Cookie:

![Cookie表格](assets/cookies1.png)

## 為Chrome、Firefox和Edge變更準備我網站的最佳方式為何？

Analytics客戶應確認其JavaScript設定是使用HTTPS來呼叫Adobe服務。 ECID會將協力廠商HTTP呼叫重新導向至其HTTPS端點，這可增加延遲，但表示您不需要變更設定。

Adobe建議您確保所有網站頁面都採用HTTPS。

### 多個網域的一個CNAME

如果您的CNAME實作設定在與網站相同的網域中，這將是第一方Cookie內容，您不需要進行變更。

不過，如果您擁有多個網域，並在所有網域上使用相同的CNAME進行資料收集，則會將其視為其他網域上的第三方Cookie。 有了Chrome 80，這些其他網域將不再顯示它。 為了讓所有瀏覽器的行為更類似，Analytics會明確將此Cookie `SameSite` 的值設為 `Lax`。 如果您在友好的第三方內容中使用此Cookie，則需要將Cookie與值一起設定，這也 `SameSite=None` 表示您必須始終使用HTTPS。 請連絡Adobe客戶服務，讓您的安全CNAME變更SameSite值。 請注意，使用ECID的Analytics客戶不需要執行此動作。

## Safari變更(ITP 2.1)對Analytics有何影響？

雖然Safari 12.1有所變更，但Adobe Experience Cloud cookie的資料集仍在收集中。 雖然Cookie的上限為7天，但在該時間內回訪您屬性的訪客會續約Cookie，並防止其再過期7天。 Safari流量的回顧視窗和回訪訪客計數可能會減少，直到Adobe更新可供使用為止。

由於7天的過期時間縮短，客戶可能會看到獨特訪客的增加。 瀏覽和頁面檢視計數不應受影響。 如果您的屬性具有季節性流量，例如稅務服務或假日零售，您可能會發現影響較大，因為此訪客不會在季節間連線。

如果您使用CNAME，訪客ID服務會將ECID儲存至伺服器端的第一方Cookie。 這可讓Cookie在完整期間持續存在。

**注意：ITP 2.1不適用於行動應用程式中的內嵌瀏覽器。**

### 受影響的第一方Cookie

透過建立的第一方Cookie `document.cookie` 會受到影響。 如果您是透過HTTP回應（伺服器端）或使用CNAME認證來設定其中任何Cookie,ITP 2.1中的變更不會影響您。下列第一方Cookie和相關的Adobe javaScript程式庫會受到影響：

* 由ECID(Experience Cloud ID)服務程式庫設定的AMCV Cookie
* Analytics舊版備援Cookie `s_fid`

作為第 `s_vi` 三方Cookie的Analytics舊版Cookie（包括2o7.net或omtrdc.net的收集目標）會繼續根據舊版ITP遭到封鎖。

總結：

* 如果您有CNAME並使用訪客ID服務— 您的實作將不受影響。

* 如果您在第一方內容中使用第一方CNAME，而不使用訪客ID服務— 您的實作將不受影響。

* 如果您在第三方內容中使用第一方Cookie網域，或與標準第三方網域名稱（例如2o7.net、omtrdc.net等）搭配使用，Safari會繼續依現有方式加以封鎖。

* 如果您使用自訂訪客ID — 這將視訪客ID的儲存方式而定。 如果您將ID儲存在第一方「用戶端」Cookie中，則會受到七天到期的約束。 如果您使用其他方式來儲存自訂ID，則需要評估您是否受到影響。

### 影響最小的資料集

頻繁返回的作用中訪客的資料集受變更影響最小。 如果您網站的內容是讓客戶每天或每週至少返回幾次，這些作用中使用者的Cookie會在到期前續訂。 社交網路、新聞和其他媒體網站最有可能有大量頻繁回訪的使用者社群。

使用作其主 `s_vi` 要訪客ID並設定有使用CNAME之第一方資料收集的客戶，不會受到ITP 2.1的影響。請注意，在無法 `s_vi` 設定的例項中，可能會使 `s_fid` 用備援Cookie，且會有7天的過期時間。

此外，使用訪客ID服務且具有第一方網域的資料集則受影響最小。

## Safari變更是否會影響我的業務？

Adobe建議客戶在變更資料收集之前，先測量其公司內部的影響。 這可依本節中提供的方法來完成。

若要評估對報告和測試的影響，請務必瞭解您已實作的訪客和Cookie追蹤類型，以及使用Safari的使用者有多少流量。 請考慮下列因素，以評估對個別業務的影響：

* 檢查Adobe程式庫設定的Cookie類型。

* 在您最新的Safari瀏覽器中開啟您的開發人員主控台。 如果您在您的第一方網域中看到上述設定的任何Cookie，這些變更可能會影響您。

* 如果您看到 `s_vi` Cookie，但未在CNAME內容中設定 `AMCV` Cookie，則您會使用CNAME來識別訪客，而且您的Analytics使用不受這些變更的影響。 如果您在CNAME中看到 `s_vi` Cookie和 `AMCV` Cookie設定，您最近或目前都在使用寬限期，而您的部分Analytics流量可能會受到影響。

* 使用Analytics可測量未在七天內回訪的訪客百分比。 如果訪客在七天內反覆回訪，您的流量可能不會受到重大影響。 如需使用Analtyics來瞭解此資訊的指示，請參閱 [Safari ITP 2.1對Adobe Experience cloud和Experience platform客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

* 從Safari瀏覽器測量您的流量百分比，以判斷進行任何變更是否有足夠的保證。 如需使用Analytics以瞭解您網站Safari流量百分比的指示，請參閱 [Safari ITP 2.1對Adobe Experience cloud和Experience platform客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 我的訪客最常使用哪些瀏覽器？

如果您想進一步瞭解訪客使用的瀏覽器，可以使用Analytics [Browser Dimension](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-browsers.html) ，判斷哪些瀏覽器最常用於您的網站。 您也可以使用Analytics維度來查看哪些瀏覽器最常根據地理區域使用。 For more information, see [GeoSegmentation](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-geosegmentation.html).

根據 [統計](https://gs.statcounter.com/browser-market-share/all)，於2019年底，各瀏覽器的全球市場份額如下：

* Chrome:~64%
* Safari:~17%
* Firefox:~4%
* 邊緣：~2%

隨著市場份額的變化，您可以參考此類統 [計資料](https://gs.statcounter.com/browser-market-share/all) ，以檢視您的實作策略。

## 如何在短期內最好地運用Safari的ITP 2.1變更？

Adobe的CNAME和受管理的認證程式正用於處理ITP變更。 Adobe Managed Certificate Program 可讓您免費對第一方 Cookie 實作新的第一方 憑證。目前，Adobe已提供數種CNAME服務（依解決方案區分），並希望在短期內運用Analytics認證方案。

任何目前具有CNAME設定且也使用Experience Cloud ID服務進行訪客身分識別的Analytics客戶，都可以利用未來的ECID程式庫更新。 這項變更將允許CNAME認證的追蹤伺服器維護ECID，並用作訪客識別的參考。 ECID程式庫的後續版本提供更多資訊。

Adobe知道並非所有ECID程式庫客戶都使用CNAMES或Analytics。 所有ECID客戶都將獲得CNAME設定，以利用相同的功能。

如果您目前未運用CNAME進行實作，則可以與客戶服務洽詢以開始程式。

## Adobe未來針對永久訪客身分識別的計畫為何？

新功能和實作包括：

* 所有Adobe解決方案的CNAME認證自助服務選項

* 彈性的訪客ID收集方法、BYOI（攜帶您自己的身分）和API-first資料收集

* Adobe Experience platform的身分圖

* 統一的Adobe資料收集方法

Adobe致力於為想要獲得個人化體驗的消費者提供更精確的個人化服務。 Adobe致力提供我們的客戶線上識別功能，協助他們符合其消費者的隱私權選擇。

## 更多資訊

如需詳細資訊，請參閱：

* [Adobe Experience Cloud:Google Chrome的Cookie更新](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Safari ITP 2.1對Adobe Experience cloud和Experience platform客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)

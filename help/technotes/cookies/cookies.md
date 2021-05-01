---
title: Adobe Analytics 與瀏覽器 Cookie
description: 瞭解追蹤預防措施如何影響由Adobe Analytics設定的協力廠商和第一方Cookie。
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 7%

---


# Adobe Analytics 與瀏覽器 Cookie

本檔案說明主要瀏覽器的追蹤防範措施如何影響由Adobe Analytics設定的協力廠商和第一方Cookie。 其中包含有關Apple的Intelligent Tracking Prevention(ITP)計畫，以及Chrome透過SameSite屬性對協力廠商Cookie的限制。

## 瀏覽器如何限制Cookie的使用？

### 協力廠商Cookie限制

在協力廠商內容中使用的Cookie已廣為淘汰。 Firefox和Safari從2019年和2020年起，依預設開始封鎖協力廠商Cookie。 Chrome已宣佈計畫在2022年某個時候停止支援第三方Cookie。 當協力廠商Cookie發生錯誤時，其實無法使用。

此外，Chrome目前僅允許Cookie在第三方內容中運作（如果Cookie的「SameSite」屬性設為「無」且標示為安全），也就是說，它們只能透過HTTPS使用。 「[什麼是SameSite Cookie屬性？](#samesite-effect)」一節提供了更多資訊，並說明它對Analytics有何影響？」

#### 哪些Adobe協力廠商Cookie會受到影響？

訪客ID服務使用[`demdex.net`](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) Cookie為不同客戶網域的訪客提供永久識別碼。 在封鎖第三方Cookie的瀏覽器上，無法進行跨網域追蹤。

### 第一方Cookie限制{#limitations-first-party-cookies}

所有主要瀏覽器皆允許使用第一方Cookie。 不過，Apple會限制透過其智慧型追蹤程式(ITP)Adobe設定的第一方Cookie的有效期。 這包括MacOS上的Safari以及iOS和iPadOS上的所有瀏覽器。

Adobe的第一方Cookie僅限7天到期或24小時到期，Apple判斷來自追蹤器的點進次數。 在7天到期的情況下，如果使用者瀏覽您的網站，然後在這7天內傳回，則Cookie的到期日會再延長7天。 不過，如果使用者瀏覽您的網站，然後在8天內回訪，則會在第二次瀏覽時視為新使用者。

目前，ITP原則適用於所有由Adobe設定的第一方Cookie，不論您是使用訪客ID服務或舊版Analytics ID(「s_vi」 Cookie)。 這些原則一度只套用至Cookie設定用戶端，而不套用至Cookie設定伺服器端（透過CNAME實作）。 不過，在2020年11月更新了ITP，以套用至CNAME實施。

#### ITP政策重大變更時間表

* 2019年2月，ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/):用戶端Cookie僅限7天到期[
* 2019年4月，ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/)[:當反向連結網域a)參與跨網站追蹤及b)最終URL包含查詢字串及／或片段識別碼時，用戶端Cookie的廣告點按時間限制為24小時。
* 2020年11月，含[CNAME遮蓋與彈回追蹤防禦](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/):ITP限制已擴充至CNAME實作。

ITP政策正在不斷演變。 如需最新政策，請參閱Webkit](https://webkit.org/tracking-prevention)中的[追蹤預防。

#### 哪些Adobe第一方Cookie會受到影響？

所有由Adobe設定的第一方Cookie和相關的JavaScript程式庫都受ITP原則影響：

* [`AMCV` ](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) Cookie由Adobe Experience Cloud訪客ID(ECID)服務程式庫所設定
* 當Analytics舊版[`s_vi` Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)使用CNAME設定為第一方資料收集時
* Analytics legacy [`s_fid` cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)，此為無法設定`s_vi`時使用的備援Cookie

#### ITP對Safari for Analytics有何影響？

ITP限制的影響會因使用者的行為而大不相同。 只有使用受ITP影響的瀏覽器（即Safari）並在7天不在場後回訪的訪客才會受到影響。 如果訪客未使用ITP瀏覽器或在七天內回訪，則不會受到影響。 請務必在Analytics中檢閱您自己的資料，以瞭解此限制的影響程度。 如需如何評估對您網站的影響的秘訣，請參閱「[如何判斷Safari變更是否影響我的業務？](#measure-itp-effect)」

如果這些限制確實會影響您的資料，您會看到：

1. 增加的訪客計為舊訪客，因為其Cookie已過期，所以會視為新訪客。 根據「訪客」量度的任何量度（例如「每位訪客的銷售額」）也會受到影響。
2. 歸因的變更。 轉換事件會系結至相同訪客先前的活動。 一旦Cookie過期，未來事件就會與新訪客產生關聯，轉換無法系結回原始訪客。

>[!NOTE]
>
>ITP技術目前不適用於行動應用程式中的內嵌瀏覽器。

## 協力廠商 Cookie 和第一方 Cookie 之間有何差異？

### 協力廠商 Cookie

協力廠商Cookie不是由使用者造訪的網站所建立。

雖然瀏覽器目前對所有第三方Cookie的處理方式相同並據以儲存，但第三方Cookie的行為方式可能不同。 透過客戶的Analytics協力廠商Cookie實作，瀏覽器會將Adobe[demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) ID儲存為協力廠商Cookie，但客戶僅會呼叫Adobe，而不會呼叫太不明或可疑的協力廠商網域。 此Cookie可跨網域提供永續性識別碼，並允許安全(HTTPS)內容。 如需詳細資訊，請參閱 [Cookie 和 Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)。

在Analytics實作中，協力廠商Cookie用於跨網域追蹤和廣告使用案例，包括重新定位廣告。 協力廠商Cookie可讓您識別訪客瀏覽您擁有的不同網域時，或在您不擁有的網站上顯示廣告時的身分。<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### 第一方 Cookie

第一方Cookie是網域特定的，由客戶網站建立，當使用者造訪網站時儲存在用戶端瀏覽器中。 所有瀏覽器通常都接受第一方Cookie，但[Safari會限制某些類型的第一方Cookie的到期時間。](#limitations-first-party-cookies)

在Analytics實作中，第一方Cookie可用來識別使用者在您網站上的時間，因此支援所有使用者活動分析。 您不需要協力廠商的Cookie就能瞭解網站活動。

如需詳細資訊，請參閱[關於第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html)。

![Cookie 比較](/help/technotes/assets/cookies2.png)

## 什麼是SameSite Cookie屬性，它對Analytics Cookie有何影響？{#samesite-effect}

隨著Chrome 80瀏覽器於2020年2月推出— 以及Firefox和Edge瀏覽器的後續版本。 sameSite Cookie屬性會對三個不同的值執行規格，以控制跨網站請求的行為：

* `None`：此設定可啟用跨網站存取，以及啟用在協力廠商內容中傳遞 Cookie。若要指定此屬性，您也必須指定 `Secure`，且所有瀏覽器請求都必須遵循 HTTPS。例如，設定 Cookie 時，您需依下列方式配對屬性的值：`Set-Cookie: example_session=test12; SameSite=None; Secure`。如果未正確標示，則較新的瀏覽器將無法使用Cookie，並遭拒。

* `Lax`:允許跨網站請求僅以同一網站Cookie傳送，以利用 *safe* (唯讀 `GET`，例如)HTTP方法進行頂層導覽。

* `Strict`：不會針對任何協力廠商網站請求傳送同網站 Cookie。只有當 Cookie 的網站與 URL 列中的網站相符時，才會傳送 Cookie。

這些瀏覽器版本的預設行為是將未指定 `SameSite` 屬性的 Cookie 視為 `SameSite=Lax`。

### Analytics如何管理SameSite Cookie屬性？

所有AdobeCookie更新都會透過Adobe伺服器處理，Adobe邊緣伺服器會設定適當的Cookie屬性。 所有第三方Cookie都已在伺服器端以適當的屬性進行更新。 您的網站不需要 JavaScript 更新。

當使用者造訪使用Cookie的任何網站時，Adobe邊緣伺服器會自動進行此次升級。 對於大部分的Adobe產品，Cookie在2020年Chrome 80發行時會有適當的標幟。 但Adobe Analytics實作則例外，這些實作使用協力廠商資料收集，而且不使用Experience Cloud訪客ID服務。 對於此類實作，您必須要求客戶服務變更標幟；如需詳細資訊，請參閱下一節中的「當您對多個網域使用一個CNAME時，變更SameSite值[」。 ](#samesite-one-cname)在變更旗標之前，這些客戶可體驗到新訪客的小幅度臨時增加，否則會標籤為舊訪客。

對於Google在`SameSite`設為`None`時已識別為Cookies處理錯誤的瀏覽器，請改為未設定`SameSite`。

下表摘要了Analytics Cookie的SameSite屬性：

![Cookie 表格](/help/technotes/assets/cookies1.png)

### 我的網站如何解決SameSite屬性的需求？

#### 使用HTTPS服務您所有的網站頁面

確認您的JavaScript組態使用HTTPS來呼叫Adobe服務。

如果您的網站使用Experience Cloud訪客ID服務，服務會將第三方HTTP呼叫重新導向至其HTTPS端點，這可能會增加延遲，但表示您不需要變更設定。

#### 對多個網域{#samesite-one-cname}使用一個CNAME時，請變更SameSite值

>[!NOTE]
>
>下列資訊僅與未使用Experience Cloud訪客ID服務的網站有關。

如果您的CNAME實作設定在與網站相同的網域中，則Cookie是在第一方內容中建立，您不需要進行變更。

不過，如果您擁有多個網域，並在所有網域上使用相同的CNAME進行資料收集，則Cookie會被視為其他網域上的第三方Cookie。 有了Chrome 80及更新版本，這些其他網域將不再顯示它。 為了讓所有瀏覽器的行為更類似，Analytics已明確將此Cookie的`SameSite`值設為`Lax`。 如果您在好記的第三方內容中使用此Cookie，則必須將Cookie設定為`SameSite=None`值，這也表示您必須一律使用HTTPS。 如果您尚未這麼做，請連絡Adobe客戶服務，讓您的安全CNAME變更SameSite值。

## 如何判斷Safari變更是否會影響我的業務？{#measure-itp-effect}

Adobe建議客戶在變更資料收集前，先測量其公司內部的影響。 您可以使用Analysis Workspace來評估ITP追蹤防範對個別業務的影響：

* 測量來自ITP管理瀏覽器的流量百分比：

   1. 建立區段，以查看有多少訪客使用ITP平台。

      ![ITP訪客的區段](/help/technotes/assets/itp-visitor-segment.png)

   2. 將區段套用至瀏覽次數，以瞭解Safari在您的使用者群中的相對使用情形。 這可讓您建立如下的表格：

      ![依ITP訪客劃分的瀏覽百分比](/help/technotes/assets/visits-vs-safari-visits.png)

* 測量使用非Safari瀏覽器且七天內未回訪的訪客百分比。 如果您的非Safari訪客在七天內反覆回訪，您的Safari流量可能不會受到重大影響。

   1. 針對非Safari流量建立如下的區段。

      ![七天後回訪的訪客區段](/help/technotes/assets/visits-after-seven-days.png)

   2. 將區段套用至瀏覽次數，以瞭解Safari在您的使用者群中的相對使用情形。 這可讓您建立如下的表格：

      ![七天後回訪的訪客百分比](/help/technotes/assets/percent-visits-after-seven-days.png)

### 在報告期間調整資料的方式

如果您的企業受到ITP追蹤防範的影響，您可能會考慮下列措施，以在報告期間調整資料。

* 建立區段以篩選掉ITP使用者。

   ![非ITP訪客的區段](/help/technotes/assets/non-itp-visitor-segment.png)

* 建立計算量度，以因應已知訪客的膨脹而調整。

   ![計算量度，以因應訪客膨脹而調整](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[可降低瀏覽器Cookie限制影響的選項](cookieless.md)
>[蘋果新應用追蹤透明框架對Adobe Analytics的影響](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)

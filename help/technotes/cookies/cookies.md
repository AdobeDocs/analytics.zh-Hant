---
title: Adobe Analytics 與瀏覽器 Cookie
description: 了解預防追蹤措施如何影響 Adobe Analytics 所設定的第三方和第一方 Cookie。
source-git-commit: b2f606e74aa0d2ab0f01ab7cbfc795bfd7cda461
workflow-type: tm+mt
source-wordcount: '1985'
ht-degree: 72%

---


# Adobe Analytics 與瀏覽器 Cookie

此文件說明主要瀏覽器的預防追蹤措施如何影響 Adobe Analytics 所設定的第三方和第一方 Cookie。 其中包括 Apple 智慧預防追蹤 (ITP) 計劃以及 Chrome 對於透過 SameSite 屬性的第三方 Cookie 的限制等相關資訊。

## 瀏覽器如何限制了 Cookie 的使用？

>[!NOTE]
>[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en#cda)和[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#comparing-cja-to-traditional-adobe-analytics)可使用人員ID（例如雜湊登入ID）拼接各個Cookie（若有）。

### 第三方 Cookie 限制

第三方內容中所使用的 Cookie 正在被大規模淘汰。 Firefox 和 Safari 分別從 2019 和 2020 年開始在預設情況下封鎖第三方 Cookie。 Chrome 已宣佈在 2022 年停止支援第三方 Cookie 的計劃。 當他們停止支援後，實際上就無法使用第三方 Cookie 了。

此外，Chrome 目前僅允許在以下條件下讓第三方內容中的 Cookie 運作：其「SameSite」屬性已設為「無」且標記為安全，這表示只能透過 HTTPS 使用這些 Cookie。 「[什麼是 SameSite Cookie 屬性以及它對 Analytics 有何影響？](#samesite-effect)」一節中有提供更多資訊

#### 哪些 Adobe 第三方 Cookie 會受到影響？

訪客ID服務使用「[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hant)」Cookie，為不同客戶網域的訪客提供永久性識別碼。 舊版Analytics ID服務「s_vi」Cookie會設為第三方Cookie，適用於未使用自訂CNAME收集網域的實施。

在封鎖第三方 Cookie 的瀏覽器上，無法使用跨網域追蹤。

### 第一方 Cookie 限制 {#limitations-first-party-cookies}

所有主要瀏覽器都允許使用第一方 Cookie。 然而，Apple 透過其智慧預防追蹤 (ITP) 計劃來限制 Adobe 所設定的第一方 Cookie 存留時間。 這會影響Safari，以及iOS和iPadOS上的所有瀏覽器。

Adobe的第一方cookie限制為7天過期，若是Apple判斷來自追蹤器的點進，則限制為24小時過期。 若為7天過期，如果使用者造訪您的網站並在7天內回訪，則Cookie的到期日會再延長7天。 不過，如果使用者造訪您的網站，並在八天內回訪，則在第二次造訪時會將他們視為新使用者。

目前 ITP 政策適用於 Adobe 所設定的所有第一方 Cookie，無論您是使用 Visitor ID 服務還是舊的 Analytics ID (「s_vi」Cookie)。 一方面，這些政策僅適用於 Cookie 設定的用戶端，而不適用於 Cookie 設定的伺服器端 (透過 CNAME 實作)。 但在 2020 年 11 月，ITP 已更新為同樣適用於 CNAME 實作。

#### ITP 政策重大變更的時間表  {#ITP-timeline}

* 2019 年 2 月推出的 [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)：用戶端 Cookie 限制為七天到期
* 2019 年 4 月推出的 [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/)：當反向連結網域 a) 涉及了跨網站追蹤及 b) 最終 URL 包含了查詢字串及/或片段識別碼時，廣告點擊的用戶端 Cookie 限制為 24 小時到期。
* 2020 年 11 月推出的 [CNAME 遮蔽和反彈追蹤防禦](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/)：ITP 限制已擴充到 CNAME 實作。

ITP 政策經常在進化中。 如需最新政策，請參閱Webkit](https://webkit.org/tracking-prevention)中的Apple [追蹤預防。

#### 哪些 Adobe 第一方 Cookie 會受到影響？

Adobe 設定的所有第一方 Cookie 及相關 JavaScript 程式庫都會受到 ITP 政策所影響：

* [Adobe Experience Cloud訪](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) 客ID(ECID)服務程式庫所設定的&quot;AMCV&quot; Cookie
* 使用CNAME設定第一方資料收集時，Analytics舊版[&quot;s_vi&quot; cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hant)
* Analytics舊版[&quot;s_fid&quot; cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)，這是無法設定&quot;s_vi&quot;時使用的備援Cookie

#### 在 Safari 中施行 ITP 對 Analytics 有何影響？

ITP限制的影響可能會因使用者的行為而大不相同。 只有使用受ITP影響的瀏覽器（例如Safari）且在七天不在後回訪的訪客會受到影響。 如果訪客未使用 ITP 瀏覽器或在七天內回訪，則不受影響。 請務必檢閱您在 Analytics 中所擁有的資料，以了解此限制影響的程度。 如需如何衡量對您網站之影響的相關秘訣，請參閱「[該如何判斷 Safari 變更是否影響我的企業？](#measure-itp-effect)」

如果這些限制確實影響了您的資料，您將會看到：

1. 訪客計數增加，因為回訪訪客的 Cookie 已到期所以被視為新訪客。 任何根據訪客量度的量度 (例如根據訪客的銷售量) 也會受到影響。
2. 歸因的變更。 歸因需仰賴將轉換事件與相同訪客先前的活動連結在一起。 Cookie過期後，後續事件就會與新訪客產生關聯。 新訪客的活動無法與先前訪客的活動系結。

>[!NOTE]
>
>ITP 技術目前不適用於行動應用程式中的內嵌瀏覽器。

## 第三方 Cookie 和第一方 Cookie 之間有何差異？

### 第三方 Cookie

第三方 Cookie 並不是由用戶造訪的網站所建立。

雖然瀏覽器目前對所有協力廠商Cookie的處理方式相同並加以儲存，但協力廠商Cookie的行為方式可能不同。 有了客戶的 Analytics 第三方 Cookie 實作，瀏覽器會將 Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=zh-Hant) ID 儲存為第三方 Cookie，但用戶端只會對 Adobe 發出呼叫，而不會對不明或可疑的第三方網域發出呼叫。 此 Cookie 可跨網域提供永續性識別碼，且允許安全 (HTTPS) 內容。 如需詳細資訊，請參閱「[Cookie 和 Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)」。

有了 Analytics 實作，第三方 Cookie 會用於跨網域追蹤及推廣使用案例，包括重定廣告目標受眾。 第三方 Cookie 可在訪客造訪您擁有的不同網域或是在非您擁有的網站上對訪客顯示廣告時，讓您識別這些訪客。<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### 第一方 Cookie

第一方 Cookie 是網域所專屬並由客戶網站所建立，而且會在用戶瀏覽網站時儲存在用戶端瀏覽器中。 所有瀏覽器通常都會接受第一方 Cookie，但 [Safari 會限制某些類型的第一方 Cookie 的到期時間](#limitations-first-party-cookies)。

在 Analytics 實作中，第一方 Cookie 是用來識別用戶何時出現在您的網站上，因此可支援對用戶活動的所有分析。 您不需要第三方 Cookie 來了解網站上的活動。

如需詳細資訊，請參閱「[關於第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hant)」。

![Cookie 的比較](/help/technotes/assets/cookies2.png)

## 什麼是 SameSite Cookie 屬性以及它對 Analytics Cookie 有何影響？ {#samesite-effect}

隨著2020年2月發行的Chrome 80瀏覽器以及Firefox和Edge瀏覽器的後續版本，SameSite Cookie屬性會針對三個不同的值強制執行規格，這些值可控管Cookie是否可在協力廠商內容中使用：

* `None`：此設定可啟用跨網站存取，以及啟用在協力廠商內容中傳遞 Cookie。若要指定此屬性，您也必須指定 `Secure`，且所有瀏覽器請求都必須遵循 HTTPS。例如，設定 Cookie 時，您需依下列方式配對屬性的值：`Set-Cookie: example_session=test12; SameSite=None; Secure`。如果未正確標示，Cookie 在較新版的瀏覽器中將無法使用，並遭到拒絕。

* `Lax`：允許僅針對採用&#x200B;*安全* (唯讀，例如 `GET`) HTTP 方法的最上層導覽傳送跨網站要求，連同相同網站的 Cookie。

* `Strict`：不會針對任何協力廠商網站請求傳送同網站 Cookie。只有當 Cookie 的網站與 URL 列中的網站相符時，才會傳送 Cookie。

這些瀏覽器版本的預設行為是將未指定 `SameSite` 屬性的 Cookie 視為 `SameSite=Lax`。

### Analytics 如何管理 SameSite Cookie 屬性？

若是使用訪客ID服務的客戶，Cookie預設會設定屬性`SameSite=None`和`secure`，這可讓這些Cookie支援第三方使用案例。

若客戶使用Analytics舊版識別碼（「s_vi」和「s_fid」Cookie），也會設定Cookie以啟用標準收集網域的第三方使用案例：adobedc.net、2o7.net和omtrdc.net。 對於使用CNAME實作的客戶，Analytics會設定`SameSite=Lax`。

>[!NOTE]
>
>如果您擁有多個網域，並在所有網域上使用相同的CNAME來收集資料，則系統會將該Cookie視為其他網域上的協力廠商Cookie。 如果您使用舊版Analytics識別碼，則可將設定更新為`SameSite=None`，以便在您的網站間共用這些Cookie。 如需詳細資訊，請參閱下一節中的「[當您對多個網域使用一個CNAME時變更SameSite值](#samesite-one-cname)」。

針對將 `SameSite` 設定為 `None` 時 Google 已識別為錯誤處理 Cookie 的瀏覽器，`SameSite` 會保留為未設定。

下表摘要列出適用於 Analytics Cookie 的 SameSite 屬性：

![Cookie 表格](/help/technotes/assets/cookies1.png)

### 我的網站要如何滿足 SameSite 屬性的要求？

#### 使用 HTTPS 服務您的所有網站頁面

確認您的 JavaScript 設定會針對 Adobe 服務的所有呼叫使用 HTTPS。

如果您的網站使用 Experience Cloud Visitor ID 服務，該服務會將第三方 HTTP 呼叫重新導向其 HTTPS 端點，這樣可能會增加延遲時間，但也表示您不需要變更您的設定。

#### 當您針對多個網域使用一個 CNAME 時，請變更 SameSite 值 {#samesite-one-cname}

>[!NOTE]
>
>以下資訊僅與不使用 Experience Cloud Visitor ID 服務的網站有關。

如果您的 CNAME 實作是在與您網站相同的網域中所設定，則會在第一方內容中建立 Cookie，而且您不需要進行變更。

但如果您擁有多個網域，並在所有網域上使用相同 CNAME 進行資料收集，則系統會將此 Cookie 視為其他幾個網域上的第三方 Cookie。 在 Chrome 80 和更高版本中，其他幾個網域上無法再看到此 Cookie。 為了讓所有瀏覽器的行為更相似，Analytics 已明確將`SameSite`此 Cookie 的值設為 `Lax`。 如果您在支援的第三方內容中使用此 Cookie，則需使用 `SameSite=None` 值設定此 Cookie，這也表示您必須一律使用 HTTPS。 如果您還沒有這樣做，請聯絡 Adobe 客戶服務，要求為您的安全 CNAME 變更 SameSite 值。

## 該如何判斷 Safari 變更是否會影響我的企業？ {#measure-itp-effect}

Adobe 建議客戶在變更資料收集之前，先在他們自己的公司內衡量變更的影響。 您可以使用 Analysis Workspace 來衡量 ITP 預防追蹤對您個別企業的影響：

* 衡量您的流量來自 ITP 控管的瀏覽器所佔的百分比：

   1. 建立區段來查看有多少訪客正在使用 ITP 平台。

      >[!NOTE]
      >
      >受ITP影響的特定瀏覽器取決於您是否使用CNAME實作。 如需詳細資訊，請參閱「[ITP政策重大變更時間表](#ITP-timeline)」。

      ![ITP 訪客適用的區段](/help/technotes/assets/itp-visitor-segment.png)

   2. 將此區段套用到訪客人數，以了解您的用戶群中 Safari 的相對使用率。 這可讓您建立如下的表格：

      ![ITP 訪客的造訪百分比](/help/technotes/assets/visits-vs-safari-visits.png)

* 衡量使用非 Safari 瀏覽器且未在七天內回訪的訪客百分比。 如果非 Safari 瀏覽器訪客在七天內重複回訪，您的 Safari 流量可能不會受到太大的影響。

   1. 針對非 Safari 流量建立如下的區段。

      ![過了七天後回訪的訪客適用的區段](/help/technotes/assets/visits-after-seven-days.png)

   2. 將此區段套用到訪客人數，以了解您的用戶群中 Safari 的相對使用率。 這可讓您建立如下的表格：

      ![過了七天後回訪的訪客百分比](/help/technotes/assets/percent-visits-after-seven-days.png)

### 在報告期間調整資料的方式

如果您的企業受到 ITP 預防追蹤的影響，您可以考慮在報告期間採取以下措施來調整您的資料。

* 建立區段來篩選掉 ITP 用戶。

   ![非 ITP 訪客適用的區段](/help/technotes/assets/non-itp-visitor-segment.png)

* 建立計算量度，以針對已知的訪客膨脹狀況進行調整。

   ![可針對訪客膨脹狀況進行調整的計算量度](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[可減輕瀏覽器 Cookie 限制之影響的選項](cookieless.md)
>[Apple 的新 App Tracking Transparency Framework 對 Adobe Analytics 的影響](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)

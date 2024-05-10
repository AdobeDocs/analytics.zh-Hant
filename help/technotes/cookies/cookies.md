---
title: Adobe Analytics 與瀏覽器 Cookie
description: 了解預防追蹤措施如何影響 Adobe Analytics 所設定的第三方和第一方 Cookie。
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: ac9221bd7d9397ed0f085245663f1f0056f7d68f
workflow-type: ht
source-wordcount: '1909'
ht-degree: 100%

---

# Adobe Analytics 與瀏覽器 Cookie

此文件說明主要瀏覽器的預防追蹤措施如何影響 Adobe Analytics 所設定的第三方和第一方 Cookie。 其中包括 Apple 智慧預防追蹤 (ITP) 計劃以及 Chrome 對於透過 SameSite 屬性的第三方 Cookie 的限制等相關資訊。

## 瀏覽器如何限制了 Cookie 的使用？

>[!NOTE]
>[跨裝置分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html#cda)和 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html#comparing-cja-to-traditional-adobe-analytics) 可以使用人員 ID (例如雜湊登入 ID) 來跨 Cookie 彙整 (如果可用)。

### 第三方 Cookie 限制

第三方內容中所使用的 Cookie 正在被大規模淘汰。 Firefox 和 Safari 分別從 2019 和 2020 年開始在預設情況下封鎖第三方 Cookie。 Chrome 已宣佈在 2023 年停止支援第三方 Cookie 的計劃。 當他們停止支援後，實際上就無法使用第三方 Cookie 了。

此外，Chrome 目前僅允許在以下條件下讓第三方內容中的 Cookie 運作：其「SameSite」屬性已設為「無」且標記為安全，這表示只能透過 HTTPS 使用這些 Cookie。 「[什麼是 SameSite Cookie 屬性以及它對 Analytics 有何影響？](#samesite-effect)」一節中有提供更多資訊

#### 哪些 Adobe 第三方 Cookie 會受到影響？

訪客 ID 服務會使用「[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)」Cookie 為跨不同客戶網域的訪客提供永續性識別碼。 舊版 Analytics ID 服務 &quot;s_vi&quot; Cookie 被設定為第三方 Cookie，用於不使用自訂 CNAME 收集網域的實作。

在封鎖第三方 Cookie 的瀏覽器上，無法使用跨網域追蹤。

### 第一方 Cookie 限制 {#limitations-first-party-cookies}

所有主要瀏覽器都允許使用第一方 Cookie。 然而，Apple 透過其智慧預防追蹤 (ITP) 計劃來限制 Adobe 所設定的第一方 Cookie 存留時間。 這會影響 Safari 以及 iOS 和 iPadOS 上的所有瀏覽器。

Adobe 的第一方 Cookie 限制為 7 天到期，或者，如果 Apple 判斷點進來自追蹤器，則為 24 小時到期。 如果是 7 天到期，則當使用者造訪您的網站然後在七天內回訪時，Cookie 的到期日會再延長七天。 但如果使用者造訪您的網站然後在八天後回訪，則會在第二次造訪時將其視為新使用者。

目前 ITP 政策適用於 Adobe 所設定的所有第一方 Cookie，無論您是使用 Visitor ID 服務還是舊的 Analytics ID (「s_vi」Cookie)。 一方面，這些政策僅適用於 Cookie 設定的用戶端，而不適用於 Cookie 設定的伺服器端 (透過 CNAME 實作)。 但在 2020 年 11 月，ITP 已更新為同樣適用於 CNAME 實作。

#### ITP 政策重大變更的時間表 {#ITP-timeline}

* 2019 年 2 月推出的 [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)：用戶端 Cookie 限制為七天到期
* 2019 年 4 月推出的 [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/)：當反向連結網域 a) 涉及了跨網站追蹤及 b) 最終 URL 包含了查詢字串及/或片段識別碼時，廣告點擊的用戶端 Cookie 限制為 24 小時到期。
* 2020 年 11 月推出的 [CNAME 遮蔽和反彈追蹤防禦](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/)：ITP 限制已擴充到 CNAME 實作。

ITP 政策經常在進化中。 如需了解最新政策，請參閱 Apple 的 [Webkit 中的預防追蹤](https://webkit.org/tracking-prevention)。

#### 哪些 Adobe 第一方 Cookie 會受到影響？

Adobe 設定的所有第一方 Cookie 及相關 JavaScript 資料庫都會受到 ITP 政策所影響：

* Adobe Experience Cloud Visitor ID (ECID) 服務資料庫設定的 [&quot;AMCV&quot; Cookie](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)
* Analytics 舊版 [&quot;s_vi&quot; Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)，前提為它是透過第一方資料收集使用 CNAME 所設定
* Analytics 舊版 [&quot;s_fid&quot; Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)，這是在無法設定 &quot;s_vi&quot; 時所使用的遞補 Cookie

#### 在 Safari 中施行 ITP 對 Analytics 有何影響？

ITP 限制的影響會因您使用者的行為而有很大的差異。 只有當訪客使用受 ITP 影響的瀏覽器 (例如 Safari) 並在七天缺席後才回訪時，才會受到影響。 如果訪客未使用 ITP 瀏覽器或在七天內回訪，則不受影響。 請務必檢閱您在 Analytics 中所擁有的資料，以了解此限制影響的程度。 如需如何衡量對您網站之影響的相關秘訣，請參閱「[該如何判斷 Safari 變更是否影響我的企業？](#measure-itp-effect)」

如果這些限制確實影響了您的資料，您將會看到：

1. 訪客計數增加，因為回訪訪客的 Cookie 已到期所以被視為新訪客。 任何根據訪客量度的量度 (例如根據訪客的銷售量) 也會受到影響。
2. 歸因的變更。 歸因依賴於將轉換事件與相同訪客的先前活動相繫結。 Cookie 過期後，後續事件將與新訪客相關聯。 新訪客的活動不能與前訪客的活動相關聯。

>[!NOTE]
>
>ITP 技術目前不適用於行動應用程式中的內嵌瀏覽器。

## 第三方 Cookie 和第一方 Cookie 之間有何差異？

### 第三方 Cookie

第三方 Cookie 並不是由用戶造訪的網站所建立。

雖然瀏覽器目前對所有第三方 Cookie 的處理方式相同，並據此方式加以儲存，但第三方 Cookie 本身可能會有不同的行為方式。 透過客戶的 Analytics 協力廠商 Cookie 實作，瀏覽器會將 Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) ID 儲存為協力廠商 Cookie，但用戶端只會對 Adobe 發出呼叫，不會對不明或可疑的協力廠商網域發出呼叫。此 Cookie 可跨網域提供永續性識別碼，且允許安全 (HTTPS) 內容。 如需詳細資訊，請參閱「[Cookie 和 Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)」。

有了 Analytics 實作，第三方 Cookie 會用於跨網域追蹤及推廣使用案例，包括重定廣告目標受眾。 第三方 Cookie 可在訪客造訪您擁有的不同網域或是在非您擁有的網站上對訪客顯示廣告時，讓您識別這些訪客。<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### 第一方 Cookie

第一方 Cookie 是網域所專屬並由客戶網站所建立，而且會在用戶瀏覽網站時儲存在用戶端瀏覽器中。 所有瀏覽器通常都會接受第一方 Cookie，但 [Safari 會限制某些類型的第一方 Cookie 的到期時間](#limitations-first-party-cookies)。

在 Analytics 實作中，第一方 Cookie 是用來識別用戶何時出現在您的網站上，因此可支援對用戶活動的所有分析。 您不需要第三方 Cookie 來了解網站上的活動。

如需詳細資訊，請參閱「[關於第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html)」。

![Cookie 的比較](/help/technotes/assets/cookies2.png)

## 什麼是 SameSite Cookie 屬性以及它對 Analytics Cookie 有何影響？ {#samesite-effect}

隨著 Chrome 80 瀏覽器在 2020 年 2 月發行及後續 Firefox 和 Edge 瀏覽器版本的推出 — SameSite Cookie 屬性會強制指定三個不同值的規格來控管 Cookie 是否可以在第三方內容中使用：

* `None`：此設定可啟用跨網站存取，以及啟用在協力廠商內容中傳遞 Cookie。若要指定此屬性，您也必須指定 `Secure`，且所有瀏覽器請求都必須遵循 HTTPS。例如，設定 Cookie 時，您需依下列方式配對屬性的值：`Set-Cookie: example_session=test12; SameSite=None; Secure`。如果未正確標示，Cookie 在較新版的瀏覽器中將無法使用，並遭到拒絕。

* `Lax`：允許僅針對採用&#x200B;*安全* (唯讀，例如 `GET`) HTTP 方法的最上層導覽傳送跨網站要求，連同相同網站的 Cookie。

* `Strict`：不會針對任何協力廠商網站請求傳送同網站 Cookie。只有當 Cookie 的網站與 URL 列中的網站相符時，才會傳送 Cookie。

這些瀏覽器版本的預設行為是將未指定 `SameSite` 屬性的 Cookie 視為 `SameSite=Lax`。

### Analytics 如何管理 SameSite Cookie 屬性？

對於使用訪客 ID 服務的客戶，Cookie 預設會設定 `SameSite=None` 和 `secure` 屬性，如此可讓這些 Cookie 支援第三方使用案例。

對於使用 Analytics 舊型識別碼 (`s_vi` 和 `s_fid` Cookie) 的客戶，Cookie 還被設定為啟用具有標準收集網域的第三方使用案例：`adobedc.net`、`2o7.net` 和 `omtrdc.net`。對於使用 CNAME 實作的客戶，Analytics 會設定 `SameSite=Lax`。

>[!NOTE]
>
>如果您擁有多個網域，並在所有網域上使用相同 CNAME 進行資料收集，則系統會將此 Cookie 視為其他幾個網域上的第三方 Cookie。 如果您使用的是舊版 Analytics 識別碼，那麼您可能需要將您的設定更新為 `SameSite=None`，以便這些 Cookie 可以在您的站點之間共用。 請參閱下一節的[當您針對多個網域使用一個 CNAME 時，請變更 SameSite 值](#samesite-one-cname)以取得詳細資訊。

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
      >受 ITP 影響的特定瀏覽器取決於您是否使用 CNAME 實作。 請參閱「[ITP 政策重大變更的時間表](#ITP-timeline)」以取得詳細資訊。

      ![ITP 訪客適用的區段](/help/technotes/assets/itp-visitor-segment.png)

   2. 將此區段套用到訪客人數，以了解您的用戶群中 Safari 的相對使用率。 這可讓您建立類似以下的表格：

      ![ITP 訪客的造訪百分比](/help/technotes/assets/visits-vs-safari-visits.png)

* 衡量使用非 Safari 瀏覽器且未在七天內回訪的訪客百分比。 如果非 Safari 瀏覽器訪客在七天內重複回訪，您的 Safari 流量可能不會受到太大的影響。

   1. 針對非 Safari 流量建立如下的區段。

      ![過了七天後回訪的訪客適用的區段](/help/technotes/assets/visits-after-seven-days.png)

   2. 將此區段套用到訪客人數，以了解您的用戶群中 Safari 的相對使用率。 這可讓您建立類似以下的表格：

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

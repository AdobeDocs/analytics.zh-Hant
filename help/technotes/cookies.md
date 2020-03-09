---
title: Adobe Analytics 與瀏覽器 Cookie
description: 瞭解 Adobe Analytics 如何處理瀏覽器的 Cookie。
translation-type: ht
source-git-commit: 3566960f546d847ed4f6ca8ecbb9c759460f4fb0

---


# Adobe Analytics 與瀏覽器 Cookie

為支援跨屬性和解決方案的持續性使用者身分識別，Adobe Analytics 會因應瀏覽器對 Cookie 處理方式所做的變更進行調整。下列常見問題集提供如何配合瀏覽器 Cookie 變更保留持續性訪客身分識別的相關資訊。

## 瀏覽器如何改變處理 Cookie 的方式？

一般而言，大部分瀏覽器對於保存協力廠商 Cookie 的方式都提高了限制。如果瀏覽器刪除或拒絕 Cookie，便會影響追蹤。Safari 瀏覽器更針對某些第一方 Cookie 設定一些額外限制。

下列清單根據瀏覽器顯示一些最近的變更：

* Chrome：自 Chrome 80 開始，為管理協力廠商 Cookie 或跨網站請求，`SameSite` 屬性的處理方式有所改變。基本上 Chrome 開發人員正在尋找完全[取代協力廠商 Cookie](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1) 的方式。

* Firefox 和 Edge：產品公告指出其瀏覽器的後續版本將遵循與 Chrome 80 所做的相同變更。

* Safari：若使用 [Safari 12.1](https://webkit.org/blog/category/privacy/)，透過 document.cookie API 設定的所有第一方永續性 Cookie (通常稱為「用戶端」Cookie)，有效期限最多為七天。

## 協力廠商 Cookie 和第一方 Cookie 之間有何差異？

### 第一方 Cookie

第一方 Cookie 是由客戶網站 (網域限定) 建立，當使用者造訪客戶網站時，會儲存在用戶端瀏覽器中。通常所有瀏覽器都接受第一方 Cookie。在第一方 Cookie Analytics 實施中，當使用 [CNAME](https://docs.adobe.com/content/help/zh-Hant/id-service/using/reference/analytics-reference/cname.html) 協調主機名稱與網域時，訪客 ID Cookie 會建立在 Adobe 節點上。然後瀏覽器會在第一方內容中接受 Cookie。如需詳細資訊，請參閱[關於第一方 Cookie](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-first-party.html)。

### 協力廠商 Cookie

協力廠商 Cookie 不是由使用者造訪的網站所建立。雖然瀏覽器目前對所有協力廠商 Cookie 的處理方式相同並據此方式加以儲存，但協力廠商 Cookie 本身可能會有重要且不同的行為方式。若使用客戶的 Analytics 協力廠商 Cookie 實施，用戶端僅會對 Adobe 發出呼叫，而不會對未知或可疑的協力廠商網域發出呼叫。這是目前為確保安全 (HTTPS) 實施 Analytics，以及使用持續性識別碼進行可靠追蹤的方法。此方法是透過設定 AppMeasurement.js 檔案來實施。如需詳細資訊，請參閱 [Cookie 和 Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html)。

![Cookie 比較](assets/cookies2.png)

## 瀏覽器目前如何儲存和管理 Analytics Cookie？

視實施而定，Analytics Cookie 的儲存方式如下：

### 協力廠商 Cookie 實施

瀏覽器目前將 Adobe [demdex.net](https://docs.adobe.com/content/help/zh-Hant/audience-manager/user-guide/reference/demdex-calls.html) ID 儲存為協力廠商 Cookie。此 Cookie 可跨網域提供持續性識別碼，且允許安全 (https) 內容。

### 第一方 Cookie 實施

設定 CNAME 後，您的使用者便可在其瀏覽器的第一方 Cookie 內容中收到 Adobe Cookie。如果協力廠商 Cookie 實施對您的使用者而言並非最佳實施，則此選項也許可行。

## 什麼是 SameSite Cookie 屬性，它對 Analytics 有何影響？

隨著 Chrome 80 瀏覽器以及 Firefox 和 Edge 瀏覽器後續版本的發行，SameSite Cookie 屬性會針對三個不同的值強制執行規格，以便控制跨網站請求的行為，如下所示：

* `None`：此設定可啟用跨網站存取，以及啟用在協力廠商內容中傳遞 Cookie。若要指定此屬性，您也必須指定 `Secure`，且所有瀏覽器請求都必須遵循 HTTPS。例如，設定 Cookie 時，您需依下列方式配對屬性的值：`Set-Cookie: example_session=test12; SameSite=None; Secure`。如果未正確標示，則較新的瀏覽器將無法使用 Cookie，且 Cookie 將遭拒。

* `Lax`：允許僅針對採用&#x200B;*安全* (唯讀，例如 `GET`) HTTP 方法的頂層導覽，以同網站 Cookie 傳送跨網站請求。

* `Strict`：不會針對任何協力廠商網站請求傳送同網站 Cookie。只有當 Cookie 的網站與 URL 列中的網站相符時，才會傳送 Cookie。

這些瀏覽器版本的預設行為是將未指定 `SameSite` 屬性的 Cookie 視為 `SameSite=Lax`。

## Adobe Analytics 如何回應這些變更？

所有 Adobe Cookie 更新都會透過 Adobe 伺服器處理，而 Adobe 已更新其邊緣伺服器以設定適當的 Cookie 屬性。Adobe 已發佈伺服器端更新，可使用適當屬性來設定其協力廠商 Cookie。您的網站不需要 JavaScript 更新。

使用者造訪使用 Cookie 的任何網站時，Adobe 邊緣伺服器會自動進行這項升級。針對大部分的 Adobe 產品，Chrome 80 發行後 Cookie 都會有適當的旗標。使用協力廠商資料收集且不使用 Experience Cloud Identity Service (ECID) 的 Adobe Analytics 實施則為例外情況。這些客戶可能會經歷暫時性的新訪客小幅度增加，原先這些新訪客會被標記為舊訪客。

針對將 `SameSite` 設為 `None` 時 Google 已識別為錯誤處理 Cookie 的瀏覽器，`SameSite` 將會保留為未設定。

下表對 Analytics Cookie 進行了摘要：

![Cookie 表格](assets/cookies1.png)

## 針對 Chrome、Firefox 和 Edge 變更為我的網站做準備的最佳方式為何？

Analytics 客戶應確認其 JavaScript 設定是使用 HTTPS 來呼叫 Adobe 服務。ECID 會將協力廠商 HTTP 呼叫重新導向至其 HTTPS 端點，這可能會增加延遲，但表示您不需要變更設定。

Adobe 建議您確保所有網頁都採用 HTTPS。

### 一個 CNAME 用於多個網域

如果您的 CNAME 實施是在與網站相同的網域中設定在，這便是第一方 Cookie 內容，您不需要進行變更。

不過，如果您有多個網域，並在所有網域上使用相同的 CNAME 進行資料收集，則系統會將其視為另外幾個網域上的協力廠商 Cookie。若使用 Chrome 80，另外幾個網域上將不再顯示該 Cookie。為了讓所有瀏覽器的行為更相似，Analytics 會明確將此 Cookie 的 `SameSite` 值設為 `Lax`。如果您在支援的協力廠商內容中使用此 Cookie，則需使用 `SameSite=None` 值設定 Cookie，這也表示您必須一律使用 HTTPS。請聯絡 Adobe 客戶服務，為您的安全 CNAME 變更 SameSite 值。請注意，使用 ECID 的 Analytics 客戶不需要執行此操作。

## Safari 變更 (ITP 2.1) 對Analytics 有何影響？

雖然 Safari 12.1 有所變更，但系統仍持續收集 Adobe Experience Cloud Cookie 的資料集。雖然 Cookie 的期限為 7 天，但訪客若在該時間內回訪您的屬性，Cookie 的期限便會重新計算，使其有效期限再延長 7 天。Safari 流量的回顧視窗和回訪訪客計數可能會減少，直到 Adobe 更新可供使用為止。

由於 7 天的有效期限縮短，客戶可能會看到獨特訪客增加。造訪和頁面檢視計數不應受影響。如果您的屬性具有季節性流量，例如稅務服務或假期零售，您可能會發現影響較大，因為季節間的訪客不相連。

如果您使用 CNAME，訪客 ID 服務會將 ECID 儲存至伺服器端第一方 Cookie 中。這可讓 Cookie 在完整期間持續存在。

**注意：ITP 2.1不適用於行動應用程式中的內嵌瀏覽器。**

### 受影響的第一方 Cookie

透過 `document.cookie` 建立的第一方 Cookie 會受到影響。如果您是透過 HTTP 回應 (伺服器端) 或使用 CNAME 憑證來設定其中任何 Cookie，ITP 2.1 中的變更並不會對您造成影響。下列第一方 Cookie 和相關的 Adobe JavaScript 程式庫則會受到影響：

* 由 ECID (Experience Cloud ID) 服務程式庫設定的 AMCV Cookie
* Analytics 舊版備援 Cookie `s_fid`

作為協力廠商 Cookie 的 Analytics 舊版 `s_vi` Cookie (包括 2o7.net 或 omtrdc.net 的收集目標) 會繼續根據舊版 ITP 遭到封鎖。

總結：

* 如果您有 CNAME 且使用訪客 ID 服務：您的實施將不會受影響。

* 如果您在第一方內容中使用第一方 CNAME，且沒有使用訪客 ID 服務：您的實施將不會受影響。

* 如果您在協力廠商內容中使用第一方 Cookie 網域，或搭配使用標準協力廠商網域名稱 (例如 2o7.net、omtrdc.net 等)，Safari 會繼續依原有方式加以封鎖。

* 如果您使用自訂訪客 ID：視您訪客 ID 的儲存方式而定。如果您將 ID 儲存在第一方「用戶端」Cookie 中，則會受到七天有效期限的約束。如果您使用其他方式來儲存自訂 ID，則需要評估您是否受到影響。

### 影響最小的資料集

經常回訪的活動中訪客之資料集，受變更影響的程度最低。如果客戶每天回訪或每週至少回訪幾次您網站的內容，那麼這些作用中使用者的 Cookie 會在到期前重新計算。社交網路、新聞和其他媒體網站最可能有大量頻繁回訪的使用者社群。

客戶若使用 `s_vi` 作為其主要訪客 ID 並使用 CNAME 設定第一方資料收集，將不會受到 ITP 2.1 的影響。請注意，在無法設定 `s_vi` 的情況下，可能會使用備援 Cookie `s_fid`，且有效期限為七天。

此外，使用訪客 ID 服務且具有第一方網域的資料集受到的影響最小。

## Safari 的變更是否會影響我的業務？

Adobe 建議客戶在對資料收集作業進行任何變更之前，先衡量會對其公司內部造成的影響。衡量方式於本節下文中提供。

若要衡量對報表和測試的影響，請務必瞭解您所實施的訪客和 Cookie 追蹤類型為何，以及使用 Safari 的使用者流量有多少。請考慮下列因素，衡量對個別業務的影響：

* 檢查 Adobe 程式庫所設定的 Cookie 類型。

* 在最新版 Safari 瀏覽器中開啟開發人員主控台。如果您在第一方網域中看到已設定上述任何 Cookie，表示這些變更可能會對您造成影響。

* 如果您在 CNAME 內容中看到 `s_vi` Cookie 但未設定 `AMCV` Cookie，表示您正使用 CNAME 來識別訪客，而且您使用 Analytics 的方式不會受到這些變更影響。如果您在 CNAME 內容中看到 `s_vi` Cookie 且已設定 `AMCV` Cookie，表示您最近或目前正在使用寬限期，而您的部分 Analytics 流量可能會受到影響。

* 使用 Analytics 測量沒有在七天內回訪的訪客百分比。如果訪客在七天內重複回訪，您的流量可能不會受到重大影響。如需使用 Analtyics 來瞭解此資訊的指示，請參閱 [Safari ITP 2.1 對 Adobe Experience Cloud 和 Experience Platform 客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

* 測量來自 Safari 瀏覽器的流量百分比，以判斷進行任何變更是否可獲得充足的保證。如需使用 Analtyics 來瞭解您網站 Safari 流量百分比的指示，請參閱 [Safari ITP 2.1 對 Adobe Experience Cloud 和 Experience Platform 客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## 我的訪客最常使用哪些瀏覽器？

如果您想進一步瞭解訪客使用的瀏覽器，可以使用 Analytics 的[瀏覽器維度](https://docs.adobe.com/content/help/zh-Hant/analytics/components/variables/dimensions-reports/reports-browsers.html)，判斷哪些瀏覽器最常用於您的網站。您也可以使用 Analytics 維度來查看各地理區域最常使用哪些瀏覽器。如需詳細資訊，請參閱[地域劃分](https://docs.adobe.com/content/help/zh-Hant/analytics/components/variables/dimensions-reports/reports-geosegmentation.html)。

根據 [StatCounter](https://gs.statcounter.com/browser-market-share/all)，2019 年底各瀏覽器的全球市占率如下：

* Chrome：~64%
* Safari：~17%
* Firefox：~4%
* Edge：~2%

隨著市占率改變，您可以參考這類[統計資料](https://gs.statcounter.com/browser-market-share/all)，審視您的實施策略。

## 如何在短期內最有效運用 Safari 的 ITP 2.1 變更？

我們正使用 Adobe 的 CNAME 和 Managed Certificate Program 處理 ITP 變更。Adobe Managed Certificate Program 可讓您免費對第一方 Cookie 實作新的第一方 憑證。目前 Adobe 提供數種 CNAME 服務 (依解決方案區分)，並期望在短期內運用 Analytics 認證計畫。

任何目前已設定 CNAME 且同時使用 Experience Cloud Identity Service 進行訪客身分識別的 Analytics 客戶，都可以利用未來的 ECID 程式庫更新。這項變更將允許經 CNAME 認證的追蹤伺服器維護 ECID，並作為訪客識別的參照使用。ECID 程式庫的後續發行版本將提供更多資訊。

Adobe 瞭解並非所有 ECID 程式庫客戶都有使用 CNAME 或 Analytics。我們將為所有 ECID 客戶提供 CNAME 設定，因此可使用相同的功能。

如果您目前並未將 CNAME 用於實施，可以向客戶服務洽詢以展開程序。

## Adobe 未來對於持續性訪客身分識別的計畫為何？

新功能和實施包括：

* 所有 Adobe 解決方案均適用的 CNAME 認證自助選項

* 彈性的訪客 ID 收集方法、BYOI (自攜身分) 和 API 優先資料收集

* Adobe Experience Platform 的身分圖

* 統一的 Adobe 資料收集方法

Adobe 致力為想獲得個人化體驗的消費者提供更精確的個人化服務。Adobe 致力為客戶提供線上身分功能，協助他們滿足其消費者對隱私選擇需求。

## 更多資訊

如需詳細資訊，請參閱：

* [Adobe Experience Cloud：Google Chrome 的 Cookie 更新](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Safari ITP 2.1 對 Adobe Experience Cloud 和 Experience Platform 客戶的影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)

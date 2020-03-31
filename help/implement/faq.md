---
title: Analytics 實施常見問題集
description: 實施的相關常見問題，以及可提供更多資訊的連結。
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Analytics 實施常見問題集

實施的相關常見問題，以及可提供更多資訊的連結。

**變數配置和與有效期之間有何差異？**

配置和有效期都是可套用至自訂變數的設定。持續存在的變數值和新的變數值並存時，*配置*&#x200B;就會開始起作用。它會判斷要保留舊值還是新值。當您不想讓變數值持續存在，*有效期*&#x200B;就會開始起作用。

**Experience Cloud 訪客 ID 與 Analytics 訪客 ID 有何不同？**

Identity Service 會指派不重複的持續性識別碼，以便在 Experience Cloud 的其他解決方案之間共用。Analytics 訪客 ID 僅供 Analytics 使用。Adobe 建議您在實施中使用 Experience Cloud 訪客 ID 服務。

**如果 Cookie 被封鎖會如何設定訪客 ID？**

標準 Cookie 無法使用時，系統會使用隨機產生的不重複 ID 在網站的網域上建立備援 Cookie。`s_vi`此 Cookie (名為 `s_fid`) 會設定 2 年的有效期，且會作為後續的備援身分識別方法。

**如何實施心率視訊追蹤？**

請參閱[在 Adobe Analytics 測量音訊和視訊](https://docs.adobe.com/content/help/zh-Hant/media-analytics/using/media-overview.html)。

**Adobe 的服務中斷會影響效能嗎？**

不可以。JavaScript 檔案並非由 Adobe 伺服器託管，所以 Adobe 中斷不會影響 AppMeasurement 程式庫。如果您使用 Adobe Experience Platform Launch，JavaScript 檔案會由 Akamai 託管，或於貴組織所決定的伺服器位置託管。

**從瀏覽器傳送資料給 Adobe 服務會降低效能嗎？**

AppMeasurement 會在 HTML 頁面內部建立影像物件，接著瀏覽器再向 Adobe 資料收集伺服器要求該影像物件。如果資料收集伺服器效能緩慢或無反應，處理該要求的執行緒會延遲，直到傳回影像或逾時。因為瀏覽器使用多個執行緒來處理影像，Adobe 中斷對頁面載入時間的影響極小，最多只會佔用一個執行緒，而其他執行緒仍持續運作。

**如何追蹤行動應用程式？**

您可以使用 Adobe Experience Platform SDK。如需詳細資訊，請參閱 [Adobe Experience Platform SDK 概述](https://aep-sdks.gitbook.io/docs/)。

**什麼是外掛程式？**

外掛程式是執行進階函數的程式碼片段。它們可擴充 AppMeasurement 的功能，讓您的實施擁有更多功能。

---
title: Analytics 實作常見問題集
description: 實作的相關常見問題，以及可提供更多資訊的連結。
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Analytics 實作常見問題集

實作的相關常見問題，以及可提供更多資訊的連結。

**變數分配與有效期之間有何差異？**

配置和過期都是您可套用至自訂變數的設定。 *當您* 有持續的變數值和新的變數值時，分配就會開始運作。 它會決定是否保留舊值或新值。 *當您不想* 讓變數值持續存在時，過期就會開始生效。

**Experience cloud訪客ID與Analytics訪客ID之間有何差異？**

Identity service會指派唯一、永續的識別碼，以便在Experience cloud的其他解決方案之間共用。 Analytics訪客ID僅供Analytics使用。 Adobe建議在您的實作中使用Experience cloud訪客ID服務。

**如果Cookie被封鎖，訪客ID如何設定？**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**如何實作心率視訊追蹤？**

請參閱[在 Adobe Analytics 測量音訊和視訊](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html)。

**Adobe的服務中斷會影響效能嗎？**

不可以。JavaScript檔案不是裝載在Adobe伺服器上，因此Adobe中斷不會影響您的AppMeasurement程式庫。 如果您使用Adobe Experience Platform Launch,JavaScript檔案會由Akamai代管，或位於您組織所決定的伺服器位置。

**從瀏覽器傳送資料至Adobe服務會降低效能嗎？**

AppMeasurement會在HTML頁面中建立影像物件，然後瀏覽器會向Adobe資料收集伺服器要求影像物件。 如果資料收集伺服器速度緩慢或沒有回應，該要求的執行緒處理會延遲，直到影像傳回或逾時為止。 因為瀏覽器使用多個執行緒來處理影像，Adobe 中斷對頁面載入時間的影響極小，最多只會佔用一個執行緒，而其他執行緒仍持續運作。

**如何追蹤行動應用程式？**

您可以使用Adobe Experience Platform SDK。 如需詳 [細資訊，請參閱Adobe Experience Platform SDK總覽](https://aep-sdks.gitbook.io/docs/) 。

**什麼是增效模組？**

外掛程式是執行進階功能的程式碼片段。 它們可擴充AppMeasurement的功能，讓您在實作中擁有更多功能。

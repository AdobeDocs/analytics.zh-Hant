---
description: 訪客移轉是將訪客 ID Cookie 從一個網域移轉至另一個網域的程序。
keywords: Analytics Implementation
title: 訪客移轉
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# 訪客移轉

訪客移轉是將訪客 ID Cookie 從一個網域移轉至另一個網域的程序。

訪客移轉可讓您在變更資料收集網域時保留訪客識別 Cookie。資料收集網域可能因下列原因而變動:

* 從 `2o7.net` 移至 `omtrdc.net` ([區域資料收集](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))。

* 您正在實作 [Experience Cloud 訪客 ID 服務](https://marketing.adobe.com/resources/help/en_US/mcvid/)，且正在從 CNAME/第一方資料收集網域移轉至 `2o7.net` 或 `omtrdc.net` ([地區資料收集](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))

* 從 `2o7.net` 或 `omtrdc.net` 移轉至 cname/第一方資料收集 ([第一方 Cookie)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)。

* 從一個 CNAME 移至另一個 CNAME (變更網域)。

設定好訪客移轉後，當使用者未使用訪客 ID Cookie 瀏覽新網域時，伺服器會重新導向至先前的資料收集主機名稱、擷取可用的訪客 ID Cookie，然後重新導向回新網域。如果在先前的主機名稱上找不到訪客 ID，則會產生新 ID。每個訪客只會發生一次。

## 訪客移轉程序 {#section_FF0C5C5CAEF343FFA1892B29311F7160}

下表列出訪客移轉的必要任務:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任務 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>開始使用:</b> <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"  >請聯絡客戶服務</a>，提供您要移轉的網域以及您想啟用的移轉期間 (30、60 或 90 天)。請務必包含不安全和安全的網域。 </p> </td> 
   <td colname="col3"> <p>使用移轉來源和目標網域的<i>確實</i>語法，建立清單。 </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>移轉主機名稱在 Adobe 資料收集伺服器上設定。客戶服務會告知您何時進行變更，讓您規劃下一步驟。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>組態變更後 6 小時以上</b>: 更新 Analytics JavaScript 程式碼中的 <code> s.trackingServer</code> 和 <code> s.trackingServerSecure</code> 變數，以使用新的資料收集伺服器。 </p> </td> 
   <td colname="col3"> <p>進行此項變更後，請使用[封包監視程式](../implement/validate/packet-monitor.md)來驗證Analtyics影像要求是否會前往更新的資料收集伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>緊接在更新 Analytics 程式碼後</b>: 測試您的網站，驗證重新導向至先前的資料收集網域正在發生。 </p> </td> 
   <td colname="col3"> <p>使用 [封包監視器](../implement/validate/packet-monitor.md)，以確認當您第一次存取您的網站或清除Cookie後，在200（確定）HTTP狀態碼之前會看到兩個302（重新導向）HTTP狀態碼。 如果任何重新導向失敗，請立即聯絡客戶服務，確認移轉是否有正確設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>在整個移轉期間</b>: 保留 DNS 記錄，讓先前的主機名稱作用中。 </p> </td> 
   <td colname="col3"> <p>先前的主機名稱必須透過 DNS 解析，否則無法進行 Cookie 移轉。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已遭取代的 visitorMigrationKey 和 visitorMigrationServer 變數 {#section_32FCEE2575944D039EA0FEBFB5814259}

從 2013 年 3 月開始，`visitorMigrationKey`、`visitorMigrationServer` 和 `visitorMigrationServerSecure` 資料收集變數已遭取代，不再使用。以前這些變數包含的資料現在儲存在 Adobe 伺服器上，提供更高的安全性。

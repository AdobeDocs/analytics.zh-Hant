---
description: 當使用者瀏覽您的網站時，Adobe 網站伺服器會設定持續 Cookie，方法為將它併入瀏覽器的 HTTP 回應中。此 Cookie 會設定在指定的資料收集網域上。
keywords: Analytics Implementation
title: Analytics 訪客 ID
topic: Developer and implementation
uuid: fa7737cc-0190-4d27-af1b-87301a715df2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Analytics 訪客 ID

當使用者瀏覽您的網站時，Adobe 網站伺服器會設定持續 Cookie，方法為將它併入瀏覽器的 HTTP 回應中。此 Cookie 會設定在指定的資料收集網域上。

當請求傳送至 Adobe 資料收集伺服器時，會檢查標題中是否有訪客 ID Cookie `s_vi`)。如果請求中有此 Cookie，便會用來識別訪客。如果請求中沒有 Cookie，則伺服器會產生獨特的訪客 ID、在 HTTP 回應標題中將其設定為 Cookie，並隨請求將其傳回。Cookie 儲存在瀏覽器中，並在後續瀏覽網站時傳回至資料收集伺服器，以便在各次瀏覽間識別訪客。

## 協力廠商 Cookie 和 CNAME 記錄 {#section_61BA46E131004BB2B75929C1E1C93139}

有些瀏覽器 (例如 Apple Safari) 不再從下列情況的網域儲存 HTTP 標題中設定的 Cookie: 不符合目前網站的網域 (這是協力廠商上下文中使用的 Cookie，或是協力廠商 Cookie)。例如，如果您位於 `mysite.com` 而您的資料收集伺服器是 `mysite.omtrdc.net`，則瀏覽器可能會拒絕從 `mysite.omtrdc.net` HTTP 標題中傳回的 Cookie。

為了避免此問題，許多客戶在進行[第一方 Cookie 實施](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)時，會為其資料收集伺服器實施 CNAME 記錄。如果已設定 CNAME 記錄將客戶網域的主機名稱對應至資料收集伺服器 (例如，將 `metrics.mysite.com` 對應至 `mysite.omtrdc.net`)，則資料收集網域現在符合網站的網域，因此可以儲存訪客 ID Cookie。如此可提高訪客 ID Cookie 被儲存的可能性，但也會造成額外負荷，因為您必須設定 CNAME 記錄以及維護資料收集伺服器的 SSL 憑證。

## 行動裝置上的 Cookie {#section_7D05AE259E024F73A95C48BD1E419851}

使用 Cookie 追蹤行動裝置時，您可使用一些設定來修改測量的發生方式。Cookie 預設期限為 5 年，但您可使用 CL 查詢參數變數 (`s.cookieLifetime`) 來變更此預設值。若要設定 cname 實施的 Cookie 位置，請使用 CDP 查詢字串 `s.cookieDomainPeriods`。若未指定值，預設為 2。而預設位置為 domain.com。對於未使用 CNAME 的實施，訪客 ID Cookie 位置位於 207.net 網域。

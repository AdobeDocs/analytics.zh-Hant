---
title: 中國的地區資料收集
seo-title: Adobe Analytics China RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# 中國的地區資料收集

Adobe 在中國大陸實施地區資料收集 (RDC) 作業，中國境內的客戶可將資料直接傳送至中國境內的資料收集中心 (DCC)，而非傳送至全球其他位置。比起將資料傳送至中國境外的 DCC，這麼做可縮短頁面載入時間，並提升資料準確度。

> [!IMPORTANT] 使用中國RDC節點有額外的成本。使用本文件所述的RDC節點在中國實施資料收集之前，請連絡貴組織的客戶經理以確認您已正確獲得此功能。

## 設定中國的追蹤伺服器

您可在任何對服務而言方便的時候將追蹤功能用於中國 RDC。對於您想要將RDC路由至中國RDC的任何數位屬性(例如行動應用程式或網頁)，請將追蹤伺服器變更為：

`<namespace>.sc.adobedc.cn`

請務必插入適當的命名空間。您通常可在現有追蹤伺服器的開頭找到這項資訊。For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. 您也可以將非 SSL 第一方 [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) 記錄指向這個新的位置。

如果您的客戶群有大部分在中國以外的地區，請勿將您的trackingServer值設為AChina RDC的所有屬性和地理位置。只有針對位於中國境內的客戶，才應將 trackingServer 設定為中國 RDC 值。否則，會對位於中國境外的使用者速度造成負面影響，因為這會強迫資料收集前往中國，然後再傳回回應。

## 識別中國境內的使用者

不論您的數位財產託管於何處，或使用哪種語言，如果您使用中國的 RDC 節點，中國的使用者將能體驗到改善之處。因此，建議的作法為判定有哪些位於中國，然後針對這些使用者使用中國 RDC。可能有助您識別這些使用者的方法包括: 

* 使用可靠的GeoIP解決方案。您可能決定使用伺服器端解決方案，輕鬆地與Adobe Experience Platform Launch(或Data Tag Management)整合。在此情況下，可在Experience Platform Launch或DTM物件中加入標準資料元素來決定位置。或者，您可能會使用用戶端 GeoIP 解決方案。在這種情況下，Experience Platform Launch可以被鎖定在用戶端程式碼中。請注意，這類解決方案可能包含提示使用者導覽至本地化的網站。這可能會造成第一頁被全域追蹤伺服器計數，而第二頁由中國的第二頁計數，這可能會導致次計數瀏覽。請遵循適用於 GeoIP 解決方案的最佳作法。對於您使用的 GeoIP 解決方案的準確度，Adobe 概不負責。

* Using site structure or the browser language (the `navigator.language / accept-language` header). 此方法的優點是可降低成本，而且可能可以提升效能。此方法的缺點是，在中國境外造訪的中文訪客會受限於受到負面影響的速度。
* 使用位於中國的代管解決方案，並根據您的主機將trackingServer設定為China RDC。這也會大幅提高速度。

## 目前限制

目前中國RDC的限制：

1. China RDC does not support first party SSL ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) in your JavaScript), or [Server-Side Forwarding](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to Adobe Audience Manager.
2. 雖然可支援 [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) 和 [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/)，不過目標和 Demdex 網域目前不在中國大陸，而且無法擁有與在中國 RDC 內相同的速度或可靠性優勢。

## Adobe 對中國客戶的承諾

Adobe 預計永久持續推動中國 RDC 的進展，且最終將新增第一方 SSL 和伺服器端轉送等功能的支援。此外，Adobe 預計在中國提供 Demdex (或同等的) 網域，以完整支援中國境內的 ECID 和 Audience Manager 收集。對於開始使用 Adobe 的中國 RDC 的客戶，歡迎無限期繼續使用此資料收集端點。

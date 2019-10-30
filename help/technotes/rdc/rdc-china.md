---
title: 中國的地區資料收集
seo-title: Adobe Analytics China RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 中國的地區資料收集

Adobe 在中國大陸實施地區資料收集 (RDC) 作業，中國境內的客戶可將資料直接傳送至中國境內的資料收集中心 (DCC)，而非傳送至全球其他位置。比起將資料傳送至中國境外的 DCC，這麼做可縮短頁面載入時間，並提升資料準確度。

> [!IMPORTANT] 使用China RDC節點會產生額外的成本。 在使用本檔案所述的RDC節點在中國實作資料收集之前，請連絡您組織的帳戶管理員，以確保您正確擁有此功能的權利。

## 為中國設定追蹤伺服器

您可在任何對服務而言方便的時候將追蹤功能用於中國 RDC。對於您要路由至China RDC的任何數位屬性（例如行動應用程式或網頁），請將追蹤伺服器變更為：

`<namespace>.sc.adobedc.cn`

請務必插入適當的命名空間。您通常可在現有追蹤伺服器的開頭找到這項資訊。For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. 您也可以將非 SSL 第一方 [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) 記錄指向這個新的位置。

若您的客戶群中有很大一部分位於中國境外，請勿將所有屬性和地區的trackingServer全球值設為中國RDC。 只有針對位於中國境內的客戶，才應將 trackingServer 設定為中國 RDC 值。否則，會對位於中國境外的使用者速度造成負面影響，因為這會強迫資料收集前往中國，然後再傳回回應。

## 識別中國的使用者

不論您的數位財產託管於何處，或使用哪種語言，如果您使用中國的 RDC 節點，中國的使用者將能體驗到改善之處。因此，建議的作法為判定有哪些位於中國，然後針對這些使用者使用中國 RDC。可能有助您識別這些使用者的方法包括: 

* 使用可靠的GeoIP解決方案。  您可能會決定使用伺服器端解決方案，輕鬆與Adobe Experience Platform Launch（或資料標籤管理）整合。 在此情況下，位置可透過在Experience Platform Launch或DTM物件中加入標準資料元素來判斷。 或者，您可能會使用用戶端 GeoIP 解決方案。在這種情況下，Experience Platform Launch可以與用戶端程式碼掛鈎。 請注意，這類解決方案可能包含提示使用者導覽至本地化的網站。這會造成全域追蹤伺服器會計算第一頁，而中國會計算第二頁的風險，而可能導致重複計算的瀏覽。 請遵循適用於 GeoIP 解決方案的最佳作法。對於您使用的 GeoIP 解決方案的準確度，Adobe 概不負責。

* Using site structure or the browser language (the `navigator.language / accept-language` header). 此方法的優點是可降低成本，而且可能可以提升效能。此方法的缺點是，在中國境外造訪的中文訪客會受限於受到負面影響的速度。
* 使用中國的代管解決方案，並根據您的主機將trackingServer設定至中國RDC。 這也將大大加快速度。

## 目前限制

China RDC的目前限制：

1. China RDC不支援第一方SSL([JavaScript中的](https://helpx.adobe.com/analytics/kb/determining-data-center.html) s.trackingServerSecure [)或](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) 伺服器端轉送至Adobe Audience Manager。
2. 雖然可支援 [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) 和 [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/)，不過目標和 Demdex 網域目前不在中國大陸，而且無法擁有與在中國 RDC 內相同的速度或可靠性優勢。

## Adobe對中國的承諾

Adobe 預計永久持續推動中國 RDC 的進展，且最終將新增第一方 SSL 和伺服器端轉送等功能的支援。此外，Adobe 預計在中國提供 Demdex (或同等的) 網域，以完整支援中國境內的 ECID 和 Audience Manager 收集。對於開始使用 Adobe 的中國 RDC 的客戶，歡迎無限期繼續使用此資料收集端點。

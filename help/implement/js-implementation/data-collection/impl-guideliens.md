---
description: 遵循這些指引，即會使用相同的 Cookie 網域，而使瀏覽在不同類型的實施之間受到追蹤。
keywords: Analytics Implementation
title: 實作指南
topic: Developer and implementation
uuid: 2917f4af-19bd-4666-ae4b-056e7e33f642
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 實作指南

遵循這些指引，即會使用相同的 Cookie 網域，而使瀏覽在不同類型的實施之間受到追蹤。

* **RSID:**[!UICONTROL 報表套裝 ID]
* **VNS:**&#x200B;訪客命名空間，用以儲存[!DNL 2o7.net]訪客 ID Cookie 之 [!DNL omtrdc.net] 或  的子網域。
* **COOKIEDOMAIN:** 您的 VNS + trackingServer。這些項目可能會隨您的資料中心與 RDC 組態而大不相同。[如果您不確定您的資料收集網域](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) ，請連絡客戶服務。

## Javascript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## 硬式編碼影像要求

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->
```

使用第一方 Cookie 實施時，`VNS.COOKIEDOMAIN.net` 可能會取代為所使用的第一方 Cookie 網域。例如，`adobe.com` 上的第一方 Cookie 會取代為類似於 `metrics.adobe.com` 的網域。

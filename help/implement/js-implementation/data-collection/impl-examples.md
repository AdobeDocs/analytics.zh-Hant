---
description: 在此以 adobe.com 為例，以下說明的實施會參考相同的 visid Cookie。
keywords: Analytics 實施
seo-description: 在此以 adobe.com 為例，以下說明的實施會參考相同的 visid Cookie。
seo-title: 實施範例
solution: Analytics
title: 實施範例
topic: 開發人員和實施
uuid: 17d8d2b2-2303-495a-b0 f9-d8 d3 c05 f3893
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 實施範例

在此以 adobe.com 為例，以下說明的實施會參考相同的 visid Cookie。

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**硬式編碼影像要求:**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

若是使用第一方 Cookie: 

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**硬式編碼影像要求:**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```


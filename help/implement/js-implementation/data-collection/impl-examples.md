---
description: 在此以 adobe.com 為例，以下說明的實施會參考相同的 visid Cookie。
keywords: Analytics Implementation
title: 實作範例
topic: Developer and implementation
uuid: 17d8d2b2-2303-495a-b0f9-d8d3c05f3893
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 實作範例

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


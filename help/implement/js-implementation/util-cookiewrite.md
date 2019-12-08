---
description: 將值將入至 Cookie。
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieWrite

將值將入至 Cookie。

**語法:**

```
s.Util.cookieWrite(key, value [,expire])
```

**參數:**

| 參數 | 說明 |
|---|---|
| key | (必要) 要在 Cookie 中寫入值的機碼。 |
| value | (選用) 要寫入至 Cookie 的值。 |
| expire | (選用) 包含 Cookie 到期日的日期物件。預設值是使用工作階段 Cookie。 |

**傳回:**

**範例:**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```


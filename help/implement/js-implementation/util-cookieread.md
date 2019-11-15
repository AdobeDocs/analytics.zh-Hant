---
description: 取得 Cookie 的值。
keywords: Analytics Implementation
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Util.cookieRead

取得 Cookie 的值。

**語法:**

```
s.Util.cookieRead(key)
```

**參數:**

| 參數 | 說明 |
|---|---|
| key | (必要) 要在 Cookie 中寫入值的機碼。 |

**傳回:**

Cookie 值，若找不到 Cookie 則為空字串。

**範例:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```


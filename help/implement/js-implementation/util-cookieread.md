---
description: 取得 Cookie 的值。
keywords: Analytics 實施
seo-description: 取得 Cookie 的值。
seo-title: Util.cookieRead
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: 開發人員和實施
uuid: 825a75c6-b804-4bfe-b23 a-907113b8 bfa6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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


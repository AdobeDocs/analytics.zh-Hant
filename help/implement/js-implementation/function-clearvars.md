---
description: 會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。
keywords: Analytics 實作
seo-description: 會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。
seo-title: s.clearVars() 函數
solution: Analytics
title: s.clearVars() 函數
topic: 開發人員和實作
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.clearVars() 函數

會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

例如:

```js
s.clearVars()
```

> [!NOTE]`clearVars()`[JavaScript 適用的 AppMeasurement](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 包含 ，但無法在 H-Code 及先前的程式碼中使用。


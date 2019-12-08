---
description: 會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。
keywords: Analytics Implementation
title: s.clearVars() 函數
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

>[!NOTE]
>
>[JavaScript 適用的 AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) 包含 `clearVars()`，但無法在 H-Code 及先前的程式碼中使用。


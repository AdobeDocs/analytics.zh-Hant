---
description: 會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。
keywords: Analytics 實施
seo-description: 會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。
seo-title: s.clearVars() 函數
solution: Analytics
title: s.clearVars() 函數
topic: 開發人員和實施
uuid: 43c425bc-15ae-4892-a5 a5-e1 defcb25 ff4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
>`clearVars()` 包含在JavaScript適用 [的AppMeasurement中，](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) 但無法用於H程式碼和先前版本中。


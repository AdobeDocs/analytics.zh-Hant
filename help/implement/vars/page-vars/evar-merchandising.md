---
title: eVar（銷售）
description: 與個別產品關聯的自訂變數。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 29%

---


# eVar（銷售）

*此說明頁面說明如何實作銷售eVar。 For information on how merchandising eVars work as a dimension, see[eVars (Merchandising)](/help/components/dimensions/evar-merchandising.md)in the Components user guide.*

## 在報表套裝設定中設定 eVar

在實作中使用eVar之前，請務必在報表套裝設定中將eVar設定為所需的語法。 請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

>[!IMPORTANT]
>
>若未正確設定銷售eVar，會導致變數的值發生意外或資料遺失。 請確定您的實作已正確設定。

## 使用產品語法實作

When &#39;Product Syntax&#39; is enabled, the merchandising category is populated directly within the `products` variable, so selecting and setting a binding event is not required. 這是建議使用的方法，您也應使用此方法，除非在發生成功事件時無法將值用於設定 `products`。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

的值 `eVar1` 被指派給產品。 所有與本產品相關的後續成功事件都會計入eVar值。

## 使用轉換變數語法實作

Conversion Variable Syntax is used when the eVar value is not available to set in the `products` variable. 此案例通常表示您的頁面沒有銷售渠道或尋找方法的內容。 在這些情況下，您會在到達產品頁面之前設定銷售變數，且值會持續存在，直到發生系結事件。

當設定期間選取的綁定事件發生時，eVar 的持續值與產品相關。For example, if `prodView` is specified as the binding event, the merchandising category is tied to the current product list only at the time the event occurs. 只有後續綁定事件才能更新已指派給產品的銷售 eVar。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

值 `"Aviary"` 被指 `eVar1` 派給產品 `"Canary"`。 所有後續與本產品相關的成功事件都會計入 `"Canary"`。 此外，銷售變數的目前值繫結至所有後續產品，直到滿足下列條件之一：

* eVar過期（根據「過期時間」設定）
* 銷售 eVar 被新值覆寫。

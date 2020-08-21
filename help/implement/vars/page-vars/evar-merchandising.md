---
title: eVar (銷售)
description: 繫結至個別產品的自訂變數。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '355'
ht-degree: 100%

---


# eVar (銷售)

*此說明頁面說明如何實作銷售 eVar。若要瞭解銷售 eVar 作為維度時的運作方式，請參閱「元件」使用指南中的[eVar (銷售)](/help/components/dimensions/evar-merchandising.md)。*

## 在報表套裝設定中設定 eVar

在實作中使用 eVar 之前，請務必在報表套裝設定中設定所需語法的 eVar。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

>[!IMPORTANT]
>
>若未正確設定銷售 eVar，將會導致變數的值不符預期或遺失資料。請確定您的實作已正確加以設定。

## 使用產品語法進行實作

「產品語法」啟用時，銷售類別會直接填入 `products` 變數中，因此不需要選取和設定捆綁事件。這是建議使用的方法，您也應使用此方法，除非在發生成功事件時無法將值用於設定 `products`。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to a different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

`eVar1` 的值會指派給產品。所有與此產品相關的後續成功事件都會計入 eVar 值中。

## 使用轉換變數語法進行實作

無法在 `products` 變數中設定 eVar 值時，可使用轉換變數語法。這種情況通常表示您的頁面沒有銷售管道或尋找方法的內容。在這種情況下，您可在到達產品頁面前先設定銷售變數，而值需持續到綑綁事件發生為止。

當設定期間選取的綁定事件發生時，eVar 的持續值與產品相關。例如，如果將 `prodView` 指定為綑綁事件，銷售類別只有在事件發生時才繫結至目前的產品清單。只有後續綁定事件才能更新已指派給產品的銷售 eVar。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = "Birds;Canary";
```

`eVar1` 的值 `"Aviary"` 會指派給產品 `"Canary"`。所有與此產品相關的後續成功事件都會計入 `"Canary"` 中。此外，銷售變數的目前值繫結至所有後續產品，直到滿足下列條件之一：

* eVar 過期 (根據「過期時間」設定)
* 銷售 eVar 被新值覆寫。

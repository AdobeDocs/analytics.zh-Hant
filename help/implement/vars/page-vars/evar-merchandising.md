---
title: eVar (銷售變數)
description: 繫結至個別產品的自訂變數。
feature: Variables
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: ht
source-wordcount: '541'
ht-degree: 100%

---

# eVar (銷售)

*此說明頁面說明如何實施作業銷售 eVar。若要瞭解銷售 eVar 作為維度時的運作方式，請參閱「元件」使用手冊中的 [eVars (銷售維度)](/help/components/dimensions/evar-merchandising.md)*。

如需銷售 eVar 如何運作的詳細討論內容，請參閱「[銷售 eVar 和產品尋找方法](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html)」。

## 在報表套裝設定中設定 eVar

在實作中使用 eVar 之前，請務必在報表套裝設定中設定所需語法的 eVar。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)。

>[!WARNING]
>
>若未正確設定銷售 eVar，將會導致變數的值不符預期或遺失資料。請確定您的實施作業已正確加以設定。

## 使用產品語法進行實施作業

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

### 使用 Web SDK 的產品語法

產品語法銷售變數會在幾個不同的 XDM 欄位底下[和 Adobe Analytics 進行對應](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html)。

* 產品語法銷售 eVar 在 `productListItems[]._experience.analytics.customDimensions.eVars.eVar1` 下對應至 `productListItems[]._experience.analytics.customDimensions.eVars.eVar250`。
* 產品語法銷售事件在 `productListItems[]._experience.analytics.event1to100.event1.value` 對應至 `productListItems[]._experience.analytics.event901to1000.event1000.value`。[事件序列化](events/event-serialization.md) XDM 欄位在 `productListItems[]._experience.analytics.event1to100.event1.id` 下對應至 `productListItems[]._experience.analytics.event901to1000.event1000.id`。

>[!NOTE]
>
>當您在 `productListItems` 下設定事件時，您不需要在事件字串中設定它們。如果在兩個地方都設定事件，則事件字串中的值優先。

以下範例顯示單一[產品](products.md) 使用多個銷售 eVar 和事件：

```js
"productListItems": [
    {
        "name": "Bahama Shirt",
        "priceTotal": "12.99",
        "quantity": 3,
        "_experience": {
            "analytics": {
                "customDimensions" : {
                    "eVars" : {
                        "eVar10" : "green",
                        "eVar33" : "large"
                    }
                },
                "event1to100" : {
                    "event4" : {
                        "value" : 1
                    },
                    "event10" : {
                        "value" : 2,
                        "id" : "abcd"
                    }
                }
            }
        }
    }
]
```

上述範例物件將傳送到 Adobe Analytics 做為 `";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"`。

## 使用轉換變數語法進行實施作業

無法在 `products` 變數中設定 eVar 值時，可使用轉換變數語法。這種情況通常表示您的頁面沒有銷售管道或尋找方法的內容。在這種情況下，您可在到達產品頁面前先設定銷售變數，而值需持續到綑綁事件發生為止。

當設定期間選取的綁定事件發生時，eVar 的持續值與產品相關。例如，如果將 `prodView` 指定為綑綁事件，銷售類別只有在事件發生時才繫結至目前的產品清單。只有後續綁定事件才能更新已指派給產品的銷售 eVar。

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

`eVar1` 的值 `"Aviary"` 會指派給產品 `"Canary"`。所有與此產品相關的後續成功事件都會計入 `"Canary"` 中。此外，銷售變數的目前值繫結至所有後續產品，直到滿足下列條件之一：

* eVar 過期 (根據「過期時間」設定)
* 銷售 eVar 被新值覆寫。

### 使用 Web SDK 的轉換變數語法

使用 Web SDK 的轉換變數語法的運作方式和實作其他 [eVar](evar.md) 和[事件](events/events-overview.md) 類似。鏡像上述範例的 XDM 如下所示：

在相同或上一個事件呼叫上設定 eVar：

```js
"_experience": {
    "analytics": {
        "customDimensions": {
            "eVars": {
                "eVar1" : "Aviary"
            }
        }
    }
}
```

設定產品字串的繫結事件和值：

```js
"commerce": {
    "productViews" : {
        "value" : 1
    }
},
"productListItems": [
    {
        "name": "Canary"
    }
]
```

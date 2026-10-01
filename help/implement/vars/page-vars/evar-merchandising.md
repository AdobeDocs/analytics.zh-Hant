---
title: eVar (銷售變數)
description: 繫結至個別產品的自訂變數。
feature: Appmeasurement Implementation
exl-id: 26e0c4cd-3831-4572-afe2-6cda46704ff3
mini-toc-levels: 3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/BdChWcR9AJqLZ0KjOxSvFAjB8-58JmmGahrpvTyFeFI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 29%
---
# eVar (銷售)

>[!BEGINSHADEBOX]

*此說明頁面說明如何實施作業銷售 eVar。 若要瞭解銷售eVar作為維度時的運作方式，請參閱「元件」使用指南中的[eVar （銷售維度）](/help/components/dimensions/evar-merchandising.md)。*

>[!ENDSHADEBOX]

銷售eVar會將值繫結至個別產品，以便涉及每個產品的成功事件都會計入與該產品繫結的值。 您可以用下列兩種方式之一設定值：

* **[!UICONTROL 產品語法]**：設定[`products`](products.md)變數中每個產品的值。
* **[!UICONTROL 轉換變數語法]**：在eVar本身中設定值。 值會繫結至包含繫結事件的點選上的產品。

如需繫結、配置和到期日如何運作，請參閱[eVar （銷售維度）](/help/components/dimensions/evar-merchandising.md)。

## 在報表套裝設定中設定 eVar

在實施中使用 eVar 之前，請務必在報告套裝設定中設定所需語法的 eVar。 請參閱「管理員指南」中的[轉換變數](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)。

>[!WARNING]
>
>若未正確設定銷售 eVar，將會導致變數的值不符預期或遺失資料。 請確定已針對您的實施作業正確設定該 eVar。

## 選擇語法

當您設定`products`變數時有銷售值可用，或相同點選中的產品需要不同值時，請使用[!UICONTROL 產品語法]。 當在產品之前知道值（例如讓訪客進入產品的搜尋詞或內部促銷活動）時，請使用[!UICONTROL 轉換變數語法]。 如需完整比較，請參閱[繫結和配置如何運作](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)。

## 使用產品語法進行實施作業

啟用[!UICONTROL 產品語法]時，銷售值會直接在`products`變數中設定，因此不會使用捆綁事件。 銷售eVar進入每個產品的最後一個區段：

```js
s.products = "[category];[name];[quantity];[revenue];[events];[eVars]";
```

請使用垂直號(`|`)在相同的產品上分隔多個銷售eVar。 即使您未使用數量、收入和事件的空白預留位置，也是必要的。 若沒有這些變數，eVar值會遭到忽略。

值會與該點選上的產品繫結。 之後的值是否取代現有的繫結取決於[!UICONTROL 配置]設定。 請參閱[繫結和配置如何運作](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)。

```js
// The bare minimum to set a merchandising eVar with product syntax
s.products = ";Example product;;;;eVar1=Example merchandising value";

// An example single product with product syntax
s.products = "Example category;Example product;1;5.99;event1=1;eVar1=Turtles";

// Tie a merchandising eVar to different values on two different products
s.products = "Birds;Scarlet Macaw;1;4200;;eVar1=talking bird,Birds;Turtle dove;2;550;;eVar1=love birds";
```

### 使用 Web SDK 的產品語法

如果使用&#x200B;[**XDM物件**](/help/implement/aep-edge/xdm-var-mapping.md)，產品語法銷售變數會使用下列XDM欄位：

* 產品語法銷售 eVar 在 `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar1` 下對應至 `xdm.productListItems[]._experience.analytics.customDimensions.eVars.eVar250`。
* 產品語法銷售事件在 `xdm.productListItems[]._experience.analytics.event1to100.event1.value` 對應至 `xdm.productListItems[]._experience.analytics.event901to1000.event1000.value`。 [事件序列化](events/event-serialization.md) XDM 欄位在 `xdm.productListItems[]._experience.analytics.event1to100.event1.id` 下對應至 `xdm.productListItems[]._experience.analytics.event901to1000.event1000.id`。

>[!NOTE]
>
>當您在 `productListItems` 下設定事件時，您不需要在事件字串中設定它們。 如果在兩個地方都設定事件，則事件字串中的值優先。

以下範例顯示單一[產品](products.md) 使用多個銷售 eVar 和事件：

```json
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

如果使用&#x200B;[**資料物件**](/help/implement/aep-edge/data-var-mapping.md)，則產品語法銷售eVar是使用與AppMeasurement `products`變數相同的語法在`data.__adobe.analytics.products`中設定。 與上述XDM範例相同的資料物件同等專案：

```json
"data": {
  "__adobe": {
    "analytics": {
      "products": ";Bahama Shirt;3;12.99;event4|event10=2:abcd;eVar10=green|eVar33=large"
    }
  }
}
```

## 使用轉換變數語法進行實施作業

無法使用eVar值在`products`變數中設定時，請使用[!UICONTROL 轉換變數語法]。 這種情況通常表示您的產品頁面沒有銷售管道或尋找方法的內容。 在這些情況下，請將銷售eVar設定在捆綁事件發生的頁面之上或之前。 值會持續存在，直到過期或被新值覆寫為止。

當點選同時包含`products`變數和選取的[!UICONTROL 銷售繫結事件]時，eVar目前的值會繫結至該點選上的每個產品。 在沒有捆綁事件的產品旁邊設定eVar不會捆綁值。 之後的繫結是否會取代現有的繫結，取決於[!UICONTROL 配置]設定。 請參閱[繫結和配置如何運作](/help/components/dimensions/evar-merchandising.md#how-binding-and-allocation-work)。

如需同時設定數個產品尋找方法eVar的範例，請參閱[最佳實務：產品尋找方法](/help/components/dimensions/evar-merchandising.md#best-practice-product-finding-methods)。

下列範例會在繫結事件之前設定銷售eVar：

```js
// Place on the same or previous page before the binding event:
s.eVar1 = "Aviary";

// Place on the page where the binding event occurs:
s.events = "prodView";
s.products = ";Canary";
```

如果[!UICONTROL 產品檢視事件]是繫結事件，則`eVar1`的值`"Aviary"`已繫結至產品`"Canary"`。 與此產品相關的後續成功事件將計入`"Aviary"`。 值`"Aviary"`也會在後續包含繫結事件的點選上繫結至產品，直到符合下列其中一個條件為止：

* eVar過期（根據[!UICONTROL 過期時間]設定）。
* 銷售 eVar 被新值覆寫。

### 使用 Web SDK 的轉換變數語法

如果使用&#x200B;[**XDM物件**](/help/implement/aep-edge/xdm-var-mapping.md)，則語法的運作方式與實作其他[eVars](evar.md)和[events](events/events-overview.md)類似。 如果使用&#x200B;[**資料物件**](/help/implement/aep-edge/data-var-mapping.md)，則語法會遵循AppMeasurement。

映象上述AppMeasurement範例的XDM如下所示。

在相同或前一次事件呼叫中設定 eVar：

```json
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

```json
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

映象上述AppMeasurement範例的資料物件如下所示。

在相同或前一次事件呼叫中設定 eVar：

```json
"data": {
  "__adobe": {
    "analytics": {
      "eVar1": "Aviary"
    }
  }
}
```

設定產品字串的繫結事件和值：

```json
"data": {
  "__adobe": {
    "analytics": {
      "events": "prodView",
      "products": ";Canary"
    }
  }
}
```


---
title: products
description: 傳送目前顯示哪些產品或購物車內有哪些產品等相關資料。
feature: Appmeasurement Implementation
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 100%

---

# products

`products` 變數會追蹤產品與相連結的屬性。此變數通常會設定在個別產品頁面、購物車頁面和購買確認頁面上。其為多值變數，這表示您可以在同一次點擊中傳送多個產品，而 Adobe 會將值解析為個別的維度項目。

>[!NOTE]
>
>如果此變數設定於點擊中，但沒有 [`events`](events/events-overview.md) 變數，則[產品檢視](/help/components/metrics/product-views.md)量度會增加 1。 請務必每個使用 `products` 變數的點擊上設定適當的事件。

## 使用 Web SDK 的產品

如果使用 [**XDM 物件**](/help/implement/aep-edge/xdm-var-mapping.md)，產品會對應至下列變數：

* 類別會對應至 `xdm.productListItems[].productCategories[].categoryID`。其使用 `productCategories[]` 陣列中的第一個項目。`lineItemId` 也正確對應，但 Adobe 建議使用 `categoryID`，因為其是標準 XDM。如果兩個 XDM 欄位皆存在，則會以 `lineItemId` 為優先。
* 產品會對應至 `xdm.productListItems[].SKU` 或 `xdm.productListItems[].name`。如果兩個 XDM 欄位皆存在，則會使用 `xdm.productListItems[].SKU`。
* 數量會對應至 `xdm.productListItems[].quantity`。
* 價格會對應至 `xdm.productListItems[].priceTotal`。
* 銷售 eVar 會對應至 `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar1` 到 `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar250`，取決於您想要與產品綁定的 eVar。
* 銷售事件會對應至 `xdm.productListItems[]._experience.analytics.event1to100.event1.value` 到 `xdm.productListItems._experience.analytics.event901to1000.event1000.value`，取決於您想要與產品綁定的事件。如果您在其中一個欄位中設定事件，該事件就會自動包含在傳送至 Adobe Analytics 的[事件](events/events-overview.md)字串中。

```json
{
  "xdm": {
    "productListItems": [{
      "productCategories": [{
        "categoryID": "Men's"
      }],
      "name": "Hiking boot",
      "quantity": 1,
      "priceTotal": 49.99
    },
    {
      "productCategories": [{
        "categoryID": "Camping"
      }],
      "name": "Hunting blind",
      "quantity": 3,
      "priceTotal": 699.69
    }]
  }
}
```

如果使用&#x200B;[**資料物件**](/help/implement/aep-edge/data-var-mapping.md)，產品變數會依照 AppMeasurement 語法使用 `data.__adobe.analytics.products`。如果您設定此欄位，XDM 物件中所設定的任何產品都會被覆寫，且不會傳送至 Adobe Analytics。

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Archery;Fletched arrow;12;159.99"
      }
    }
  }
}
```

## 使用 Adobe Analytics 擴充功能的產品

在 Adobe Experience Platform 資料彙集中，沒有專用欄位可設定這個變數；不過，市面上有多個第三方擴充功能可提供協助。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下[!UICONTROL 「目錄」]檢視所有可用的擴充功能。
4. 搜尋 &quot;product&quot; 一字，幾個可用來協助設定此變數的擴充功能隨即會顯示。

您可以使用其中一個擴充功能，或依照下方的 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 中的 s.products，以及 Analytics 擴充功能的自訂程式碼編輯器

`s.products` 變數是字串，其中包含每個產品的多個分隔欄位。 在字串中以分號 (`;`) 分隔每個欄位。

* **類別**(選用)：產品類別。此欄位的長度上限為 100 個位元組。
* **產品名稱** (必要)：產品的名稱。 此欄位的長度上限為 100 個位元組。
* **數量** (選用)：此產品在購物車內的數量有多少。此欄位僅適用於購買事件的點擊。
* **價格** (選用)：小數形式的產品總價。如果數量超過一個，請將價格設定為總價，而非個別產品價格。調整此值的貨幣，使其與 [`currencyCode`](../config-vars/currencycode.md) 變數相符。請勿在此欄位中加入貨幣符號。此欄位僅適用於購買事件的點擊。
* **事件** (選用)：與產品相連結的事件。請使用垂直號 (`|`) 分隔多個事件。如需詳細資訊，請參閱[事件](events/events-overview.md)。
* **eVar** (選用)：與產品相連結的銷售 eVar。請使用垂直號 (`|`) 分隔多個銷售 eVar。如需詳細資訊，請參閱[銷售 eVar](evar-merchandising.md)。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

此變數支援同一個點擊中的多個產品，因此對於購物車和包含多種產品的購買活動非常有價值。整個`products`字串的最大長度為 64k 位元組。請在字串中以逗號 (`,`) 分隔每項產品。

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>請移除產品名稱、類別和銷售 eVar 值中的所有分號、逗號和垂直號。如果產品名稱包含逗號，AppMeasurement 會將其解析為新產品的開頭。這個錯誤的解析會拋出產品字串剩餘的部分，導致維度和報表中的資料不正確。

## 範例

在省略欄位及納入多個產品時，`products` 變數是有彈性的。這種彈性可能會導致您很容易遺漏分隔字元，致使實施傳送錯誤的資料給 Adobe。

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)，您可以逐一查看 `digitalData.product` 物件陣列：

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```

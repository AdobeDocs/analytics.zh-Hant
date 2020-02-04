---
title: products
description: 傳送顯示或顯示在購物車中的產品相關資料。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# products

變數 `products` 會追蹤與其關聯的產品和屬性。 此變數通常設定在個別產品頁面、購物車頁面和購買確認頁面上。 此變數為多值變數，這表示您可以在相同點擊中傳送多個產品，而Adobe會將值剖析為個別的維度值。

> [!NOTE] 如果此變數在點擊中設定，而變數中沒有購物車事 `events` 件，「產品檢視」量度會增加1。 請確定您在每次點擊時設定了適當的購物車事件。

## Adobe Experience Platform Launch中的產品

Launch中沒有專用欄位可設定此變數；不過，有多個協力廠商擴充功能可提供協助。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一 [!UICONTROL 下「目錄] 」以檢視所有可用的延伸模組。
4. 搜尋詞&quot;product&quot;，此詞會顯示數個可用來協助設定此變數的擴充功能。

您可以使用其中一個擴充功能，或依照下方的AppMeasurement語法使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.products

變 `s.products` 數是字串，每個產品包含多個分隔欄位。 每個產品在所有欄位中最多可包含100個位元組。 在字串中以分號(`;`)分隔每個欄位。

* **類別** （選用）:總體產品類別。 您的組織會決定如何將產品分組為類別。
* **產品名稱** （必要）:產品名稱。
* **數量** （可選）:購物車中有多少個此產品。 此欄位僅適用於購買事件的點擊。
* **價格** （可選）:產品總價小數。 如果數量超過一個，請將價格設定為總價，而非個別產品價格。 對齊此值的貨幣以符合變 `currencyCode` 數。 請勿在此欄位中加入貨幣符號。 此欄位僅適用於購買事件的點擊。
* **事件** （可選）:系結至產品的事件。 使用垂直號(`|`)分隔多個事件。 如需詳 [細資訊](events/events-overview.md) ，請參閱事件。
* **eVar** （選用）:系結至產品的銷售eVar。 使用管道(`|`)分隔多個銷售eVar。 如需詳 [細資訊，請參閱](../../../components/c-variables/c-merch-variables/var-merchandising.md) 「銷售eVar」。

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

此變數支援相同點擊中的多個產品。 它對於購物車和包含多種產品的購買非常有價值。 雖然每個產品有100位元組的限制，但變數的總長 `products` 度為64K。 在字串中以逗號(`,`)分隔每個產品。

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

> [!IMPORTANT] 請務必從產品名稱、類別和銷售eVar值中移除所有分號、逗號和垂直號。 如果產品名稱包含逗號，AppMeasurement會將其剖析為新產品的開頭。 這個錯誤的剖析會拋出產品字串的其餘部分，導致維度和報表中的資料不正確。

## 範例

在省略 `products` 欄位並包含多個產品時，變數是有彈性的。 這種彈性可讓您輕鬆遺漏分隔字元，而分隔字元會導致您的實作傳送不正確的資料給Adobe。

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product,;Example product";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

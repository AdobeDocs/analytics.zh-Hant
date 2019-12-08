---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# products

此變數可用來追蹤產品和產品類別，以及購買數量和購買價格。產品通常會與購物車事件或 事件一起設定。


<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>我們已於 2016 年 1 月更新自動設定 *`prodView`* 事件的邏輯，這會在有 *`product`* 但無 *`event`* 時發生。此更新可能會導致 *`prodView`事件增加。**`prodViews`* 數目增加的條件僅限於:
>
>1. events 變數只包含無法辨識的事件，例如 *`shoppingCart`* 或 *`cart`* 等無效事件。
   >
   >
1. *`products`* 變數不是空的。
>
>
這可能導致的副作用，在於 *`prodView`* 事件所觸發的銷售 eVar 可能會與空的 *`product`* 相關聯，但唯有 *`product list`* 只包含無效產品時 (例如只有分號，未列出任何產品)，才會發生這種情況。

*`products`* 變數會追蹤使用者在您的網站上與產品的互動情形。例如，產品變數可追蹤某項產品被檢視、新增至購物車、結帳和購買的次數。此外也可追蹤您的網站上各個商品銷售類別的相對效力。以下是使用產品變數時的常見情況。

此&#x200B;*`products`*&#x200B;變數一律應與成功事件一起設定。

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>「<span class="wintitle">products</span>」字串的大小上限為 64k。 </p> </td> 
   <td> 產品 </td> 
   <td> 產品 <p>類別 (選用) </p> <p>收入 (選用) </p> <p>件數 (選用) </p> <p>自訂事件 (選用) </p> <p>eVar (選用) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**語法**

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| 欄位 | 定義 |
|---|---|
| 類別 | 包含相關聯產品類別。在第 15 版中，產品可與多個類別相關聯，這會修正第 14 版中存在的限制。如果您先前未記錄產品類別，則鼓勵您開始對第 15 版的報告套件填寫此欄位。 |
| 產品 | (必要) 用以追蹤產品的識別碼。此識別碼可用來填入「產品」報表。請確實在整個結帳程序中使用相同的識別碼。 |
| 數量 | 購買產品的件數。此欄位必須與購買事件一起設定，才能記錄下來。 |
| 價格 | 請參考已購買的組合總品質成本 (單位 x 個別單位價格)，而非參考個別價和。此欄位必須與購買事件一起設定，才能記錄下來。 |
| 事件 | 與指定之事件相關聯的貨幣事件。請參閱[產品特有的貨幣事件](https://helpx.adobe.com/analytics/kb/comparing-event-types.html)及[整張訂單貨幣事件](https://helpx.adobe.com/analytics/kb/comparing-event-types.html)。 |
| eVar | 與指定之產品相關聯的銷售 eVar 值。請參閱[銷售變數](/help/components/c-variables/c-merch-variables/var-merchandising.md)。 |

包含在以下的值  *`products`*&#x200B;變數中包括的值是根據您正在記錄的事件類型。省略類別時，必須以類別/產品分隔字元 (;) 作為預留位置。僅在需要其他分隔字元，來區分您將包括的參數時，才需要這些分隔字元，如此頁面上的範例所示。

**設定產品與非購買事件**

*`products`* 變數必須與成功事件一起設定。

**設定產品與購買事件**

*`purchase`* 事件應設定於訂購程序的最終確認 (「感謝您」)頁面。產品名稱、類別、數量和價格全都會擷取到&#x200B;*`products`* 變數中。雖然 *`purchaseID`* 變數並非必要項目，但建議您最好使用，以防止出現重複訂單。

**產品特有貨幣事件**

如果貨幣事件收到 *`products`* 變數中的值 (而不是 events 變數)，則僅適用於該值。這有助於追磫產品特有折扣、產品出貨，以及類似值。例如，如果您已將事件 1 設為追蹤產品出貨，則具有 "4.50" 運送費用的產品可能會出現，如下所示:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

在此範例中，值 4.50 直接與 "Running Shoes" 產品相關聯。如果已將 event1 新增至產品報告，則您將看到 "4.50" 針對 "Running Shoes" 細項列出。與 Price 類似，此值應該反映所列出之數量的總金額。如果您有 2 個項目，每個項目的運送費用為 4.50，則 event1 應為 "9.00"。

**整張訂單貨幣事件**

如果貨幣事件收到事件清單中的值 (而不是 *`products`* 變數)，則是用於 *`products`* 變數中的所有產品。這在追蹤整張訂單的折扣、運費及類似的價格時很有用，不必修改產品價格或在產品清單中個別追蹤。

例如，如果您已將 event10 設定為包含整張訂單的折扣，則享有 10% 折扣的購買可能會如下所示: 

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

在貨幣事件報表中，報表總計代表已刪除重複資料的事件總計 (在此範例中，是指報告時段的折扣金額總計)，而非每項產品的事件值總和。例如，您將看到 "9.95" 同時針對 "Running Shoes" 和 "Running Socks" 列出，而且總金額也將為 "9.95"。

> [!NOTE]如果在 *`products`* 變數和 *`events`* 變數中針對同一個數值/貨幣事件指定某個值，則會使用來自 *`events`* 的值。

**缺陷、問題和提示**

* *`products`* 變數一律應與成功事件 (一或多個) 一起設定。若未指定成功事件，預設事件將是 prodView。

* 在填入產品前，請先移除產品和類別名稱中的所有逗號和分號。
* 移除所有的 HTML 字元 (註冊符號、商標等)。
* 移除價格中的貨幣符號 ($)。

**範例**

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>


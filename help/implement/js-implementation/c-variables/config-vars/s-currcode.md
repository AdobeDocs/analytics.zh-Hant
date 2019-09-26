---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.currencyCode

 變數會決定要對收入套用的轉換率。

所有金額都會以您所選擇的貨幣儲存。若該貨幣與  *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | cc | 轉換 &gt; 購買 &gt; 收入 所有顯示收入或金額值的轉換報表 | "USD" |

若您的網站可讓訪客以多種貨幣購買商品，您應使用 *`currencyCode`* 變數確定收入會以適當的貨幣儲存。For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. 資料收集在接收到資料後，會使用目前的轉換率將 40 歐元轉換為等值的美元。

若您以多種貨幣販售商品，則應在 HTML 頁面上填入 *`currencyCode`* 變數，而不是在 JavaScript 檔案中。If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the  to equal the base currency of your report suite. *`currencyCode`*&#x200B;接著，您應先轉換所有的收入，再將其傳送至 [!DNL Analytics] 中。

對於收入和任何貨幣事件都會套用貨幣轉換。這些事件是用來加總類似於收入的值 (例如稅金和運費) 的事件。收入和貨幣事件指定於產品字串中。如需產品的詳細資訊，請參閱 [events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html).

## 語法和可能的值

```js
s.currencyCode="currency_code"
```

## 範例

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## 組態設定

Adobe [!DNL Customer Care] 可變更報表套裝的預設貨幣設定。當您變更報表套裝的基本貨幣時，系統中的現有收入並不會轉換。新收入值則全都會據以轉換。

## 缺陷、問題和提示

* 若您發現報表中的收入金額高得離譜，請確定報表套裝的 *`currencyCode`* 變數和基本貨幣皆正確設定。
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* 貨幣事件不應用在非貨幣用途上。若您需要計算非貨幣的任意值或動態值，請使用[!UICONTROL 數值]事件類型。
* 當 *`currencyCode`* 變數空白，則不會套用轉換。

For more information, see [Currency Codes](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html).

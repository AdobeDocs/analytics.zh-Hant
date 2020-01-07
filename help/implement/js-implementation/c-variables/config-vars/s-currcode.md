---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.currencyCode

 變數會決定要對收入套用的轉換率。

所有金額都會以您所選擇的貨幣儲存。若該貨幣與 *`currencyCode`* 中指定的貨幣相同，或 *`currencyCode`* 空白，則不會套用轉換。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | cc | 轉換 &gt; 購買 &gt; 收入所有顯示收入或金額值的轉換報表 | "USD" |

若您的網站可讓訪客以多種貨幣購買商品，您應使用   *`currencyCode`* 變數確定收入會以適當的貨幣儲存。例如，如果報表套裝的基本貨幣是美元，而您以 40 歐元販售某項產品，則應在 HTML 頁面上使用「EUR」填入 *`currencyCode`*。資料收集在接收到資料後，會使用目前的轉換率將 40 歐元轉換為等值的美元。

若您以多種貨幣販售商品，則應在 HTML 頁面上填入  *`currencyCode`* 變數，而不是在 JavaScript 檔案中。若要使用您自己的轉換率 (而不是 Adobe 使用的轉換率)，請將 *`currencyCode`* 設為等於報表套裝的基本貨幣。接著，您應先轉換所有的收入，再將其傳送至 [!DNL Analytics] 中。

對於收入和任何貨幣事件都會套用貨幣轉換。這些事件是用來加總類似於收入的值 (例如稅金和運費) 的事件。收入和貨幣事件指定於產品字串中。如需產品的詳細資訊，請參閱[events](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/analytics-basics/ref-events.html).

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

* 如果您意外發現報表中有大量收入，請確保已正確設定報表套裝的 *`currencyCode`* 變數和基本貨幣。
* *`currencyCode`* 變數不具永久性，亦即此變數必須傳入相同的影像要求中，做為收入或其他貨幣相關度量。
* 貨幣事件不應用在非貨幣用途上。若您需要計算非貨幣的任意值或動態值，請使用[!UICONTROL 數值]事件類型。
* 當  *`currencyCode`* 變數空白，則不會套用轉換。

如需詳細資訊，請參閱[貨幣代碼](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/currency.html)。

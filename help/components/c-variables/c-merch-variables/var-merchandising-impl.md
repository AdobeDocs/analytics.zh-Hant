---
description: 說明如何啟用和實施銷售變數。
keywords: Analytics Implementation;merchandising;variable;product syntax;Conversion Variable Syntax;s.products
solution: Analytics
title: 實作銷售變數
topic: Developer and implementation
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 實作銷售變數

說明如何啟用和實施銷售變數。

## 啟用銷售變數

「管理工具&gt;報表套裝&gt;轉換變數」下 **[!UICONTROL 的任何自訂eVar]** ，都可 **[!UICONTROL 以啟用銷售]** 功能 ****。

![](assets/merch-enable.png)

| 設定 | 說明 |
|--- |--- |
| 過期時間 | 說明銷售值可持續多久。 |
| 銷售 | **** 產品語法：值在中設定 `s.products`。<br>**** 轉換變數語法：值會設定在指定的銷售eVar中。 |
| 銷售綁定事件 (僅限轉換變數語法) | 指出產品何時應繫結至目前銷售類別。按住Ctrl鍵並按一下清單中的多個項目，即可選取多個事件。 選取「轉換變數語法」時，才能選取事件。 |

## 使用產品語法來實施

啟用「產品語法」時，銷售類別會直接填入產品變數，因此不需要選取和設定綁定事件。這是建議使用的方法，您也應使用此方法，除非在發生成功事件時無法將值用於設定 `s.products`。

### 語法

```js
s.products="category;product;quantity;price;event_incrementer;eVarN=merch_category|eVarM=merch_category2";
```

### 範例

```js
s.events="prodView";
s.products=";Snow Goggles;;;;eVar1=goggles";
```

eVar1的值「護目鏡」會指派給產品「滑雪鏡」。 與此產品相關的所有後續成功事件 (產品新增、結帳、購買等) 都評給「護目鏡」。

## 使用轉換變數語法來實施

無法使用 eVar 值來設定 `s.products` 時，應使用轉換變數語法。這通常表示您的頁面沒有銷售管道或尋找方法的上下文。在這種情況下，您必須在到達產品頁面前先設定銷售變數，且值需持續到綁定事件發生為止。

當設定期間選取的綁定事件發生時，eVar 的持續值與產品相關。例如，如果指定 prodView 為綁定事件，銷售類別只有在發生事件時才繫結至目前產品清單。只有後續綁定事件才能更新已指派給產品的銷售 eVar。

### 語法

在系結事件前置於相同或上一頁：

```js
s.eVar1="merchandising_category";
```

在發生系結事件的頁面上放置：

```js
s.events="prodView";
s.products="category;product";
```

### 範例

在瀏覽的第1頁：

```js
s.eVar1="Outdoors"
```

在瀏覽的第2頁：

```js
s.events="prodView";
s.products=";Snow Goggles";
```

eVar1的值「戶外」會指派給產品「雪鏡」。 所有與本產品相關的後續成功事件（產品新增、結帳、購買等）都歸入「雪鏡」。 此外，銷售變數的目前值繫結至所有後續產品，直到滿足下列條件之一:

* eVar 過期 (根據「過期時間」設定)
* 銷售 eVar 被新值覆寫。

## 外部其他資訊

[進階轉換語法銷售](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/) : [!DNL analyticsdemystified.com]

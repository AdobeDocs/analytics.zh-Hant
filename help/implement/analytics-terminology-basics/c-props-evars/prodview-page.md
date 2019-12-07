---
description: 產品變數可用來追蹤產品和產品類別 (以及購買數量和購買價格)。
keywords: Analytics Implementation;products variable;product view;success event
title: 詳細產品檢視頁面
topic: Developer and implementation
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 詳細產品檢視頁面

產品變數可用來追蹤產品和產品類別 (以及購買數量和購買價格)。

成功事件在設定時應一律搭配 *`products`* 變數。

```js
s.events="prodView"
```

> [!NOTE]在實施中會將 *`prodView`* 視為事件，但在介面中並無相同的彈性。*`prodView`* 事件是產品的一個例項，只能在 *`products`* 報表中使用。Adobe 建議您在 *`custom`* 事件外也應使用 *`prodView`* 事件。如此，您即可同時檢視產品檢視度量與其他轉換報表中的其他度量。

```js
s.products=";diamond earrings (54321)"
```

> [!NOTE]產品字串語法必須以分號開頭。這是傳統的語法需求。這在過去會用來分隔類別和產品，但在您想變更產品分類的方式時，介面中可能會因此受到限制。為使您的報告保有最大的彈性，最好將其保留為空白，並使用「分類」來設定類別。

## 購物車頁面 (scOpen、scAdd、scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd"
s.products=";SKU"
```

## 第一個結帳頁面 {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout"
s.products=";SKU"
```

## 確認頁面 {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase"
s.products=";SKU"
```

> [!NOTE]雖然在產品字串中使用 SKU 可能會讓 *`products`* 報表較不易讀取，但在您之後想要將產品分類時可提供最佳彈性。您可以從 SKU 建立類別，以指出塗裝、製造商、類別和子類別。

當&#x200B;*`products`* 變數與 *`purchase`* 事件一起設定時，購買數量和購買價格總計會納入產品值中，如前所述。

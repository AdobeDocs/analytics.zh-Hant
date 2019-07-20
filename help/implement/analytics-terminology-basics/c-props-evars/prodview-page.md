---
description: 產品變數可用來追蹤產品和產品類別 (以及購買數量和購買價格)。
keywords: Analytics實作；產品變數；產品檢視；成功事件
seo-description: 產品變數可用來追蹤產品和產品類別 (以及購買數量和購買價格)。
seo-title: 詳細的產品檢視頁面
solution: Analytics
title: 詳細的產品檢視頁面
topic: 開發人員和實施
uuid: 464c9daf-b042-4fb8-8ca6-e104 c0 bcef45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 詳細的產品檢視頁面

產品變數可用來追蹤產品和產品類別 (以及購買數量和購買價格)。

A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

>[!NOTE]
>
>*`prodView`* 雖然在實施中視為事件，但介面中並沒有相同的彈性。The *`prodView`*event is an instance of the product and is only available in the *`products`* report. Adobe recommends you use a *`custom`* event in addition to the *`prodView`* event. 如此，您即可同時檢視產品檢視度量與其他轉換報表中的其他度量。

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>產品字串語法必須以分號開始。這是傳統的語法需求。這在過去會用來分隔類別和產品，但在您想變更產品分類的方式時，介面中可能會因此受到限制。為使您的報告保有最大的彈性，最好將其保留為空白，並使用「分類」來設定類別。

## 購物車頁面 (scOpen、scAdd、scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## 第一個結帳頁面 {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=”;SKU" 
```

## 確認頁面 {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. 您可以從 SKU 建立類別，以指出塗裝、製造商、類別和子類別。

當&#x200B;*`products`* 變數會與 *`purchase`* 事件一起設定，購買數量和購買價格總計會納入產品值中，如上面所示。

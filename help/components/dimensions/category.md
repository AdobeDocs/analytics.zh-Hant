---
title: 類別
description: 點擊的產品類別。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---


# 類別

「類別」維度會報告點擊的產品類別。如果您的實作使用 `products` 變數，且您想要查看產品類別的相關量度 (例如最暢銷商品或最常檢視的商品)，此維度就十分實用。如果您的網站上沒有任何產品，此維度可能會刻意保留為空白。

## 將資料填入此維度中

此維度會參考 [`products`](/help/implement/vars/page-vars/products.md) 變數中字串的第一個部分。第一個分號 (`;`) 前面的所有項目都會填入此維度。

## 維度項目

由於此變數以您實作中的自訂字串為基礎，因此您的組織會決定維度項目。Adobe 建議您使用「產品」和「類別」維度將個別產品分組為有意義的類別。

>[!TIP]
>
>在舊版的 Adobe Analytics 中，「類別」維度因其處理架構而受到了某些限制。這些限制已移除，而讓您得以使用任何量度和任何劃分。

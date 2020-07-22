---
title: 類別
description: 點擊的產品類別。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# 類別

「類別」維度會報告點擊的產品類別。 對於使用變數且想要查看產 `products` 品類別相關量度（例如最暢銷商品或最常檢視的商品）的實作而言，它非常有用。 如果您的網站上沒有任何產品，此維度可能會故意空白。

## 將資料填入此維度

此維引用變數中字串的第一部分 [`products`](/help/implement/vars/page-vars/products.md) 。 第一個分號(`;`)前的所有內容都會填入此維度。

## 維度項目

由於此變數是以實作中的自訂字串為基礎，因此您的組織會決定維度項目。 Adobe建議您使用「產品」和「類別」維度，將個別產品分組為有意義的類別。

>[!TIP]
>
>在舊版Adobe Analytics中，「類別」維度的某些限制是由於其處理架構的緣故。 這些限制已移除，可讓您使用任何度量和任何劃分。

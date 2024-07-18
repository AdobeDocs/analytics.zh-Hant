---
title: 產品
description: 產品的名稱。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 91%

---

# 產品

「產品」[維度](overview.md)會報告點選中的產品名稱。 如果您的實施作業使用 `products` 變數，且您想要查看產品的相關量度 (例如最暢銷商品或最常檢視的商品)，此維度就十分實用。如果您的網站上沒有任何產品，此維度可能會刻意保留為空白。

## 將資料填入此維度中

此維度會參考 [`products`](/help/implement/vars/page-vars/products.md) 變數中字串的第二個部分。第一個和第二個分號 (`;`) 之間的字元會填入此維度。

## 維度項目

由於此變數以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。Adobe 建議您為產品建立統一的命名慣例。如果您想以不同方式將產品分組，或提供更好記的名稱，可使用[分類](../classifications/c-classifications.md)。Adobe 建議同時使用「產品」和「類別」維度。

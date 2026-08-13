---
title: 產品
description: 產品的名稱。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 91%

---

# 產品

「產品」[維度](overview.md)會報告點選中的產品名稱。 如果您的實施作業使用 `products` 變數，且您想要查看產品的相關量度 (例如最暢銷商品或最常檢視的商品)，此維度就十分實用。 如果您的網站上沒有任何產品，此維度可能會刻意保留為空白。

## 將資料填入此維度中

此維度會參考 [`products`](/help/implement/vars/page-vars/products.md) 變數中字串的第二個部分。 第一個和第二個分號 (`;`) 之間的字元會填入此維度。

## 維度項目

由於此變數以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。 Adobe 建議您為產品建立統一的命名慣例。 如果您想以不同方式將產品分組，或提供更好記的名稱，可使用[分類](../classifications/classifications-overview.md)。 Adobe 建議同時使用「產品」和「類別」維度。

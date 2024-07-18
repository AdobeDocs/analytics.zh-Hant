---
title: 產品檢視
description: 檢視產品頁面的次數。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 72%

---

# 產品檢視

「產品檢視」[量度](overview.md)會顯示任何產品被檢視的次數。 如果您想要查看檢視次數最多的產品，或想瞭解產品檢視總數在一段時間內的趨勢，此量度就十分實用。

## 此量度的計算方式

此量度會計算符合下列&#x200B;**任一條件**&#x200B;的點擊次數：

* 值 `prodView` 存在於 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中；或
* 已設定[`products`](/help/implement/vars/page-vars/products.md)變數，且`events`變數是空的。

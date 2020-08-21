---
title: 產品檢視
description: 檢視產品頁面的次數。
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '94'
ht-degree: 100%

---


# 產品檢視

「產品檢視」量度會顯示任何產品被檢視的次數。如果您想要查看檢視次數最多的產品，或想瞭解產品檢視總數在一段時間內的趨勢，此量度就十分實用。

## 此量度的計算方式

此量度會計算符合下列&#x200B;**任一條件**&#x200B;的點擊次數：

* 值 `prodView` 存在於 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中；或
* 變數 [`products`](/help/implement/vars/page-vars/products.md) 已設定，且 `events` 變數中沒有任何購物車事件。任何非自訂的事件 (`event1` - `event1000`) 都是購物車事件。
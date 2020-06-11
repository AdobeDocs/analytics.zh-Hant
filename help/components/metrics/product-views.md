---
title: 產品檢視
description: 產品頁面的檢視次數。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# 產品檢視

「產品檢視」量度會顯示任何產品被檢視的次數。 當您想要查看您最常檢視的產品，或查看總產品檢視次數隨時間的趨勢時，此量度很實用。

## 此度量的計算方式

此度量會計算符合下列任一 **項** 的點擊數：

* 該值 `prodView` 存在於變 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 量中； 或
* 變數 [`products`](/help/implement/vars/page-vars/products.md) 已設定，且變數中不存在任何購物車 `events` 事件。 任何非自訂(`event1` - `event1000`)的事件都是購物車事件。
---
title: 購物車
description: 訪客在購物車中新增其第一項產品的點擊次數。
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 932a6c1452d4710b11c1ce5551c845ef6721f137
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 56%

---

# 購物車

「購物車」量度會顯示訪客在購物車中新增他們的第一個產品時的點擊次數。

## 此量度的計算方式

此量度會計算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `scOpen` 存在的點擊次數。

## 「購物車」、「購物車視圖」和「購物車添加」之間的差異

由於「購物車」、「購物車視圖」和「購物車添加」是需要實施的事件，因此您的組織將決定這些度量之間的確切差異。 但是，Adobe為以下邏輯設計了這些度量：

* 當訪客將其第一項產品新增至購物車時，「購物車」只會在每次購買時觸發一次。
* 每次訪問者查看購物車時，「購物車視圖」都會觸發。
* 每項新增至購物車的產品都會觸發「購物車新增」。

當客戶將其第一個產品添加到購物車時，預期行為是「購物車」和「購物車添加」觸發器。 同樣地，這些並非具體準則；您的組織會決定確切的實作邏輯。

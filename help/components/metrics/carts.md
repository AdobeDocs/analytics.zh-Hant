---
title: 購物車
description: 訪客在購物車中新增其第一項產品的點擊次數。
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 45%

---

# 購物車

「購物車」[量度](overview.md)會顯示訪客在購物車中新增其第一項產品的點選次數。

## 此量度的計算方式

此量度會計算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `scOpen` 存在的點擊次數。

## 「購物車」、「購物車檢視」和「購物車新增」之間的差異

由於「購物車」、「購物車檢視」和「購物車新增」是需要實作的事件，因此您的組織會決定這些量度之間的確切差異。 不過，Adobe為下列邏輯設計這些量度：

* 當訪客將其第一項產品新增至購物車時，「購物車」只會在每次購買時觸發一次。
* 每次訪客檢視其購物車時，都會觸發「購物車檢視」。
* 每項新增至購物車的產品都會觸發「購物車新增」。

當客戶將其第一個產品新增到購物車時，預期行為是「購物車」和「購物車新增」都會觸發。 同樣地，這些並非具體準則；您的組織會決定確切的實作邏輯。

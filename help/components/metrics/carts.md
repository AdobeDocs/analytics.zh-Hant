---
title: 購物車
description: 訪客在購物車中新增其第一項產品的點擊次數。
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '135'
ht-degree: 100%

---

# 購物車

「購物車」量度會顯示訪客在購物車中新增他們的第一個產品時的點擊次數。

## 此量度的計算方式

此量度會計算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `scOpen` 存在的點擊次數。

## 「購物車」與「購物車檢視」的差異

由於「購物車」和「購物車檢視」是需要實作的事件，因此您的組織會決定這兩個量度之間的確切差異。不過，Adobe 為下列項目設計這些量度：

* 當訪客將其第一項產品新增至購物車時，「購物車」只會在每次購買時觸發一次。
* 每項新增至購物車的產品都會觸發「購物車新增」。

對於第一項產品，會同時觸發「購物車」和「購物車新增」。同樣地，這些並非具體準則；您的組織會決定確切的實作邏輯。

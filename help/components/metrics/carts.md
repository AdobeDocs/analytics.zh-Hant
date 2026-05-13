---
title: 購物車
description: 訪客在購物車中新增其第一項產品的點擊次數。
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 45%

---

# 購物車

「購物車」[量度](overview.md)會顯示訪客在購物車中新增其第一項產品的點選次數。

## 此量度的計算方式

此量度會計算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `scOpen` 存在的點擊次數。

## 「購物車」、「購物車檢視」和「購物車新增」之間的差異

由於「購物車」、「購物車檢視」和「購物車新增」是需要實作的事件，因此您的組織會決定這些量度之間的確切差異。 不過，Adobe針對下列邏輯設計這些量度：

* 當訪客將其第一項產品新增至購物車時，「購物車」只會在每次購買時觸發一次。
* 每次訪客檢視其購物車時，都會觸發「購物車檢視」。
* 每項新增至購物車的產品都會觸發「購物車新增」。

當客戶將其第一個產品新增到購物車時，預期行為是「購物車」和「購物車新增」都會觸發。 同樣地，這些並非具體準則；您的組織會決定確切的實作邏輯。

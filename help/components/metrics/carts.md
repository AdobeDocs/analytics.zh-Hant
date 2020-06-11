---
title: 購物車
description: 訪客將其第一個產品新增至購物車的點擊數。
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 購物車

「購物車移除」量度顯示訪客從購物車中移除某物的次數。 當您想要瞭解客戶不再對產品感興趣的轉換漏斗部分時，此度量會很有幫助。

## 此度量的計算方式

此度量會計算變數中存 `scOpen` 在的點擊 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 數。

## 「購物車」與「購物車檢視」的差異

由於「購物車」和「購物車檢視」是需要實作的事件，因此您的組織會決定這兩個量度之間的精確差異。 但是，Adobe為下列項目設計這些量度：

* 當訪客將第一個產品新增至購物車時，「購物車」只會在每次購買時觸發一次。
* 每個新增至購物車的產品都會觸發「購物車新增」。

對於第一個產品，「購物車」和「購物車新增」觸發器都是。 同樣，這些指導方針並不具體； 您的組織會決定確切的實施邏輯。

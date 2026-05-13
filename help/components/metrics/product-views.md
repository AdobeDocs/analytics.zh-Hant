---
title: 產品瀏覽數
description: 檢視產品頁面的次數。
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
TQID: https://experienceleague.adobe.com/bspBkiEAfkwBQwWV3-KoDKDRNGLogCKkSXvY2Cpyv-M
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
source-wordcount: 80
ht-degree: 72%

---

# 產品瀏覽數

「產品檢視」[量度](overview.md)會顯示任何產品被檢視的次數。 如果您想要查看檢視次數最多的產品，或想瞭解產品檢視總數在一段時間內的趨勢，此量度就十分實用。

## 此量度的計算方式

此量度會計算符合下列&#x200B;**任一條件**&#x200B;的點擊次數：

* 值 `prodView` 存在於 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中；或
* 已設定[`products`](/help/implement/vars/page-vars/products.md)變數，且`events`變數是空的。

---
title: 機器人產品發生次數
description: 「機器人產品發生次數」量度會顯示符合機器人規則且已從Analytics報表中排除的產品字串子點選次數。
feature: Metrics
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 3ba8d2cce29a1965c85789c3fd0543c23533e3a8
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%
---
# 機器人產品發生次數

「機器人產品發生次數」 [量度](overview.md)顯示符合[機器人規則](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)的子點選數。

由於機器人報表會與報表套裝的其他資料分開，因此此量度僅適用於下列維度：

* [機器人名稱](../dimensions/bot-name.md)
* [產品](../dimensions/product.md)
* 以時間為基礎的維度（例如，[Day](../dimensions/day.md)、[Week](../dimensions/week.md)或[Month](../dimensions/month.md)）

搭配此量度使用任何其他維度不會傳回資料。

## 此量度的計算方式

Adobe會檢查每個具有[產品字串](/help/implement/vars/page-vars/products.md)的子點選，檢視它是否符合您組織已設定的機器人規則。 如果指定的子點選符合機器人規則，則會將該子點選從報表中排除，而此量度會增加一。

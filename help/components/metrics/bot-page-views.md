---
title: 機器人頁面檢視次數
description: 符合機器人規則的頁面檢視次數。
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# 機器人頁面檢視次數

「機器人頁面檢視」 [量度](overview.md) 顯示相符的頁面點選數 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

由於機器人報表會與報表套裝的其他資料分開，因此此量度僅適用於下列維度：

* [機器人名稱](../dimensions/bot-name.md)
* [頁面](../dimensions/page.md)
* 以時間為主的維度(例如 [日](../dimensions/day.md)， [周](../dimensions/week.md)，或 [月](../dimensions/month.md))

搭配此量度使用任何其他維度不會傳回資料。

## 此量度的計算方式

Adobe會檢查每個頁面點選，檢視其是否符合您組織已設定的機器人規則。 如果指定的點選符合機器人規則，頁面點選會從報表中排除，而此量度會增加一。 此量度不包含連結追蹤點選([`tl()`](/help/implement/vars/functions/tl-method.md))。

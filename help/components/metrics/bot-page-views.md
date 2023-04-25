---
title: 機器人頁面檢視
description: 符合機器人規則的頁面檢視次數。
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 4%

---

# 機器人頁面檢視

「機器人頁面檢視」量度會顯示符合的頁面點擊數 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

由於機器人報表與其餘的報表套裝資料分開，因此此量度只適用於下列維度：

* [機器人名稱](../dimensions/bot-name.md)
* [頁面](../dimensions/page.md)
* 以時間為基礎的維度(例如 [日](../dimensions/day.md), [周](../dimensions/week.md)，或 [月](../dimensions/month.md))

搭配此量度使用任何其他維度不會傳回資料。

## 此量度的計算方式

Adobe會檢查每個頁面點擊，查看其是否符合貴組織設定的機器人規則。 如果指定的點擊符合機器人規則，則頁面點擊會從報表中排除，而此量度會增加1。 此量度不包含連結追蹤點擊([`tl()`](/help/implement/vars/functions/tl-method.md))。

---
title: 機器人發生次數
description: 符合機器人規則的點選次數。
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 4%

---

# 機器人發生次數

「機器人發生次數」量度會顯示相符的點選次數 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

由於機器人報表獨立於報表套裝的其餘資料，因此此量度僅適用於下列維度：

* [機器人名稱](../dimensions/bot-name.md)
* [頁面](../dimensions/page.md)
* 以時間為基礎的維度(例如 [日](../dimensions/day.md)， [周](../dimensions/week.md)，或 [月](../dimensions/month.md))

搭配此量度使用任何其他維度不會傳回資料。

## 此量度的計算方式

Adobe會檢查每次點選，檢視它是否符合您組織已設定的機器人規則。 如果指定的點選符合機器人規則，該點選就會從報表中排除，而此量度會增加一。 此量度包含兩個頁面檢視([`t()`](/help/implement/vars/functions/t-method.md))和連結追蹤點選([`tl()`](/help/implement/vars/functions/tl-method.md))，而 [機器人頁面檢視](bot-page-views.md) 不要包含連結追蹤點選。

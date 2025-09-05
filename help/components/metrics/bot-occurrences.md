---
title: 機器人發生次數
description: 符合機器人規則的點選次數。
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# 機器人發生次數

「機器人發生次數」 [量度](overview.md)顯示符合[機器人規則](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)的點選數。

由於機器人報表會與報表套裝的其他資料分開，因此此量度僅適用於下列維度：

* [機器人名稱](../dimensions/bot-name.md)
* [頁面](../dimensions/page.md)
* 以時間為基礎的維度（例如，[Day](../dimensions/day.md)、[Week](../dimensions/week.md)或[Month](../dimensions/month.md)）

搭配此量度使用任何其他維度不會傳回資料。

## 此量度的計算方式

Adobe會檢查每次點選，檢視其是否符合您組織已設定的機器人規則。 如果指定的點選符合機器人規則，該點選就會從報表中排除，而此量度會增加一。 此量度包含頁面檢視([`t()`](/help/implement/vars/functions/t-method.md))和連結追蹤點選([`tl()`](/help/implement/vars/functions/tl-method.md))，而[機器人頁面檢視](bot-page-views.md)不包含連結追蹤點選。

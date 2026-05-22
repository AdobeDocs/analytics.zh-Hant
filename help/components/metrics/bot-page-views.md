---
title: 機器人頁面檢視次數
description: 符合機器人規則的頁面檢視次數。
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
TQID: https://experienceleague.adobe.com/Y0r2fzF87dep4NsrbJGCC9OnqBHrZozCh2DovNc90KQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 125
ht-degree: 11%

---

# 機器人頁面檢視次數

「機器人頁面檢視」的[量度](overview.md)顯示符合[機器人規則](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)的頁面點選數。

由於機器人報表會與報表套裝的其他資料分開，因此此量度僅適用於下列維度：

* [機器人名稱](../dimensions/bot-name.md)
* [頁面](../dimensions/page.md)
* 以時間為基礎的維度（例如，[Day](../dimensions/day.md)、[Week](../dimensions/week.md)或[Month](../dimensions/month.md)）

搭配此量度使用任何其他維度不會傳回資料。

## 此量度的計算方式

Adobe會檢查每個頁面點選，檢視其是否符合您組織已設定的機器人規則。 如果指定的點選符合機器人規則，頁面點選會從報表中排除，而此量度會增加一。 此量度不包含連結追蹤點選([`tl()`](/help/implement/vars/functions/tl-method.md))。

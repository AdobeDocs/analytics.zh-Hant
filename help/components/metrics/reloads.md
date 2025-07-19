---
title: 重新載入
description: 重新載入頁面的次數。
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: c9b7c32adfb44a04ab792d12ca049106b3009710
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 21%

---

# 重新載入

「重新載入」[量度](overview.md)顯示重新載入期間維度專案出現的次數。 訪客重新整理瀏覽器是觸發重新載入的最常見方式。

## 此量度的計算方式

此量度會計算[頁面](../dimensions/page.md)維度包含與上次點選相同值的點選次數。

重新載入的概念會套用至「頁面」維度，無論您在報表中使用哪個維度。 例如，如果您使用[eVar1](../dimensions/evar.md)作為維度，使用「重新載入」作為量度，此表格會顯示重新載入期間每個eVar值出現的次數（兩個連續的頁面值）。 它不會顯示兩個連續eVar1值存在的次數。

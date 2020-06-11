---
title: 例項
description: 變數已設定（且未持續）的點擊數。
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# 例項

「例項」度量顯示影像請求中明確定義維度的次數。 有些維度(例如 [eVar](../dimensions/evar.md))會在設定的點擊之後保留維度值。 當您想要查看維度值設定次數而沒有該值持續存在的點擊時，此度量很實用。

## 此度量的計算方式

在報表套裝中的所有點擊中，只包含在影像請求中明確設定維度值的點擊。 有些維度(例如 [eVar](../dimensions/evar.md))會持續存在超過其設定的點擊。 頁面檢 [視和發生](page-views.md)[次數等度量](occurrences.md) ，會同時計算初始值和持續值。 此量度不會計入持續值。
---
title: 例項
description: 變數已設定（且未持續）的點擊數。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# 例項

「例項」度量顯示影像請求中明確定義維度的次數。 有些維度(例如 [eVar](../dimensions/evar.md))會在設定的點擊之後保留維度項目。 當您想要查看維度項目設定次數而沒有該值持續存在的點擊時，此度量很有用。

## 此度量的計算方式

在報表套裝中的所有點擊中，只包含在影像請求中明確設定維度項目的點擊。 有些維度(例如 [eVar](../dimensions/evar.md))會持續存在超過其設定的點擊。 頁面檢 [視和發生](page-views.md)[次數等度量](occurrences.md) ，會同時計算初始值和持續值。 此量度不會計入持續值。
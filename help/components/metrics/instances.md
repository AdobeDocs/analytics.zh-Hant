---
title: 例項
description: 變數經設定 (且不持續存在) 的點擊次數。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '129'
ht-degree: 100%

---


# 例項

「例項」量度會顯示某個維度明確定義於影像要求中的次數。有些維度 (例如 [eVar](../dimensions/evar.md)) 在其設定所在的點擊過後仍會保存維度項目。如果您想要查看某個維度項目在加以保存的值點擊不存在的情況下進行設定的次數，此量度就十分實用。

## 此量度的計算方式

在報表套裝中的所有點擊中，僅納入在影像要求中明確設定維度項目的點擊。有些維度 (例如 [eVar](../dimensions/evar.md)) 在其設定所在的點擊過後仍會持續存在。[頁面檢視](page-views.md)和[發生次數](occurrences.md)之類的量度，會同時計入初始值和持續值。此量度不會計入持續值。
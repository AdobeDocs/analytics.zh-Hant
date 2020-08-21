---
title: 例項
description: 變數經設定 (且不持續存在) 的點擊次數。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 例項

「例項」量度會顯示某個維度明確定義於影像要求中的次數。Some dimensions, such as [eVars](../dimensions/evar.md), persist dimension items past the hit they are set on. 當您想要查看維度項目設定次數而沒有該值持續存在的點擊時，此度量很有用。

## 此量度的計算方式

在報表套裝中的所有點擊中，只包含在影像請求中明確設定維度項目的點擊。 有些維度 (例如 [eVar](../dimensions/evar.md)) 在其設定所在的點擊過後仍會持續存在。[頁面檢視](page-views.md)和[發生次數](occurrences.md)之類的量度，會同時計入初始值和持續值。此量度不會計入持續值。
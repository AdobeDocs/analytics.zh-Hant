---
title: 發生次數
description: 變數設定或持續存在的點擊數。
translation-type: tm+mt
source-git-commit: 422e99d9ea70f0192443d7ebc3631c6bf99e7591
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# 發生次數

「發生次數」量度會顯示指定維度設定或持續存在的點擊數。 當您將工作區中的維度拖曳至空白畫布時，Adobe會自動將此度量套用至專案。

## 此度量的計算方式

在報表套裝中的所有點擊中，包含定義或保留維度項目的點擊。 有些維度(例如 [eVar](../dimensions/evar.md))會持續存在超過其設定的點擊。 頁面檢 [視和發生](page-views.md)[次數等度量](occurrences.md) ，會同時計算初始值和持續值。

## 與類似度量比較

* **發生次數與例[項](instances.md)**: 發生次數會計算設定或保存維度項目的點擊。 例項不包含維度項目持續存在的點擊。
* **發生次數與頁[面檢視次數](page-views.md)**: 發生次數包括所有點擊類型，包括頁面檢視追蹤呼叫([`t()`](/help/implement/vars/functions/t-method.md))和連結追蹤呼叫([`tl()`](/help/implement/vars/functions/tl-method.md))。 頁面檢視度量僅包含頁面檢視追蹤呼叫，並排除連結追蹤呼叫。

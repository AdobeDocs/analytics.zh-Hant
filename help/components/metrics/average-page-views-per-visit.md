---
title: 每次造訪的平均頁面檢視
description: 指定維度項目在瀏覽中出現的平均次數。
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 46%

---


# 每次造訪的平均頁面檢視

「每次造訪的平均頁面檢視」維度會顯示對您所需的維度發生的平均頁面檢視次數。對於以時間為基礎的維度，您可以瞭解造訪中的平均頁面檢視次數在一段時間內的趨勢。當您想要瞭解維度項目在瀏覽中的顯示頻率時，此度量很有幫助。

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. 如果您單獨使用此量度，則會取得包含每次瀏覽異常頁面檢視的維度項目，這通常不有價值。

## 此量度的計算方式

此量度的計算公式為 [`Page views`](page-views.md)` divided by `[`Visits`](visits.md)。

## 高於 100% 的百分比

此量度常包含高於 100% 的百分比。分母是整個維度的每次瀏覽平均頁面檢視次數，分子是維度項目的每次瀏覽平均頁面檢視次數。 如果整個維度的每次瀏覽平均頁面檢視次數低於指定維度項目的每次瀏覽平均頁面檢視次數，您會看到超過100%的百分比。 依此量度排序的排名報表，會顯示異常的「每次造訪的平均頁面檢視」值，而這類值通常沒有價值。Adobe 建議在排名報表中依其他量度　(例如[造訪](visits.md)) 進行排序。
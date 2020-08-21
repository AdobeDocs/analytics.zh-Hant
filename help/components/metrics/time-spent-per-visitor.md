---
title: 每位訪客逗留時間 (秒)
description: null
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 54%

---


# 每位訪客逗留時間 (秒)

「每位訪客逗留時間（秒）」量度顯示訪客在整個存留期內與指定維度項目互動的平均時間。

由於處理架構不同，此量度在 Data Warehouse 中無法使用。

## 此量度的計算方式

此量度使用下列公式：[`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md)。

## 高於 100% 的百分比

此量度常包含高於 100% 的百分比。分母是整個維度的每位訪客逗留時間，分子是維度項目每位訪客逗留時間。 如果整個維度的每位訪客逗留時間低於指定維度項目的每位訪客逗留時間，您會看到超過100%的百分比。 依此量度排序的排名報表，會顯示異常的每位訪客逗留時間值，而這類值通常沒有價值。Adobe 建議在排名報表中依其他量度　(例如[造訪](visits.md)) 進行排序。

如需更多關於逗留時間的一般資訊，請參閱[逗留時間概觀](time-spent.md)。

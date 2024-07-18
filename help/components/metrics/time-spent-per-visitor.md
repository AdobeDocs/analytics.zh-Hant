---
title: 每位訪客逗留時間 (秒)
description: 「每位訪客逗留時間 (秒)」量度會顯示訪客在其整個期限內與指定維度項目互動的平均時間量。
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 85%

---

# 每位訪客逗留時間 (秒)

[!UICONTROL 每位訪客逗留時間（秒）] [量度](overview.md)會顯示訪客在其整個期限內與指定維度專案互動的平均時間量。

由於處理架構不同，此量度在 Data Warehouse 中無法使用。

## 此量度的計算方式

此量度使用下列公式：[`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md)。

## 高於 100% 的百分比

此量度常包含高於 100% 的百分比。分母是整個維度的每位訪客逗留時間，分子是維度項目的每位訪客逗留時間。如果整個維度的每位訪客逗留時間低於指定維度項目的每位訪客逗留時間，您就會看到高於 100% 的百分比。依此量度排序的排名報表，會顯示異常的每位訪客逗留時間值，而這類值通常沒有價值。Adobe 建議在排名報表中依其他量度　(例如[造訪](visits.md)) 進行排序。

如需更多關於逗留時間的一般資訊，請參閱[逗留時間概觀](time-spent.md)。

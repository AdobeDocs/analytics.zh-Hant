---
title: 每位訪客逗留時間 (秒)
description: 「每位訪客逗留時間 (秒)」量度會顯示訪客在其整個期限內與指定維度項目互動的平均時間量。
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
TQID: https://experienceleague.adobe.com/NFmA2Q80h2WOTRwoJ882aFMG60y2HKngR0Ew0qnxb8o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 182
ht-degree: 85%

---

# 每位訪客逗留時間 (秒)

[!UICONTROL 每位訪客逗留時間（秒）] [量度](overview.md)會顯示訪客在其整個期限內與指定維度專案互動的平均時間量。

由於處理架構不同，此量度在 Data Warehouse 中無法使用。

## 此量度的計算方式

此量度使用下列公式：[`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md)。

## 高於 100% 的百分比

此量度常包含高於 100% 的百分比。 分母是整個維度的每位訪客逗留時間，分子是維度項目的每位訪客逗留時間。 如果整個維度的每位訪客逗留時間低於指定維度項目的每位訪客逗留時間，您就會看到高於 100% 的百分比。 依此量度排序的排名報表，會顯示異常的每位訪客逗留時間值，而這類值通常沒有價值。 Adobe 建議在排名報表中依其他量度　(例如[造訪](visits.md)) 進行排序。

如需更多關於逗留時間的一般資訊，請參閱[逗留時間概觀](time-spent.md)。

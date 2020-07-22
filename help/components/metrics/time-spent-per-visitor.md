---
title: 每位訪客逗留時間 (秒數)
description: null
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 6%

---


# 每位訪客逗留時間 (秒數)

「每位訪客逗留時間（秒）」量度顯示訪客在整個存留期內與指定維度項目互動的平均時間。

由於資料倉庫的處理架構不同，此量度在資料倉庫中無法使用。

## 此度量的計算方式

此量度使用公式 [`Total seconds spent`](total-seconds-spent.md)`divided by`[`Unique visitors`](unique-visitors.md)。

## 百分比高於100%

此量度常包含100%以上的百分比。 分母是整個維度的每位訪客逗留時間，分子是維度項目每位訪客逗留時間。 如果整個維度的每位訪客逗留時間低於指定維度項目的每位訪客逗留時間，您會看到超過100%的百分比。 依此量度排序排名報表會顯示每個訪客值的異常逗留時間，這通常沒有價值。 Adobe建議在排名報表中依其他度量( [例如](visits.md)「瀏覽」)排序。

如需 [逗留時間的詳細資訊](time-spent.md) ，請參閱逗留時間概觀。

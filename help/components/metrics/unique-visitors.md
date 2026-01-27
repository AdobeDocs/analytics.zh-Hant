---
title: 不重複訪客
description: 不重複訪客識別碼的數目。
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: f26f406848ab26092738089aac64ed9b4fc08019
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 100%

---

# 不重複訪客

「不重複訪客」[量度](overview.md)會顯示該維度項目的訪客 ID 數目。這是確認流量時最常用的量度之一，因為它可讓您概略了解維度項目的使用頻率。例如，某位訪客可能在一個月內每天造訪您的網站，但這仍會計為單一不重複訪客。

如果您使用「[跨裝置分析](../cda/overview.md)」，此量度會被「[不重複裝置](unique-devices.md)」量度取代。

## 每日、每週、每月、每季和每年不重複訪客

Analysis Workspace 會根據報告的顆粒度處理不重複訪客。例如，如果您使用[日](../dimensions/day.md)維度，則會看到每個維度項目的每日不重複訪客。但在計算報表總計時，則會針對自由格式表格的日期範圍刪除不重複訪客的重複項目。

## 此量度的計算方式

此量度會計算指定維度項目的不重複訪客識別碼數量。請參閱[訪客識別概觀](/help/implement/id/overview.md)，以深入了解 Adobe Analytics 如何識別不重複訪客。

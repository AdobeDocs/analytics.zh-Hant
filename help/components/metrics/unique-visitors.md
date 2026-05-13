---
title: 不重複訪客
description: 不重複訪客識別碼的數目。
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
TQID: https://experienceleague.adobe.com/A0NvwoGPFLuS4e857eH-nMgmzAmz0EuGVQVDNBgiN4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 100%

---

# 不重複訪客

「不重複訪客」[量度](overview.md)會顯示該維度項目的訪客 ID 數目。 這是確認流量時最常用的量度之一，因為它可讓您概略了解維度項目的使用頻率。 例如，某位訪客可能在一個月內每天造訪您的網站，但這仍會計為單一不重複訪客。

如果您使用「[跨裝置分析](../cda/overview.md)」，此量度會被「[不重複裝置](unique-devices.md)」量度取代。

## 每日、每週、每月、每季和每年不重複訪客

Analysis Workspace 會根據報告的顆粒度處理不重複訪客。 例如，如果您使用[日](../dimensions/day.md)維度，則會看到每個維度項目的每日不重複訪客。 但在計算報表總計時，則會針對自由格式表格的日期範圍刪除不重複訪客的重複項目。

## 此量度的計算方式

此量度會計算指定維度項目的不重複訪客識別碼數量。 請參閱[訪客識別概觀](/help/implement/id/overview.md)，以深入了解 Adobe Analytics 如何識別不重複訪客。

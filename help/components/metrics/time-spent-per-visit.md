---
title: 每次造訪逗留時間 (量度)
description: 維度項目的每次造訪逗留時間。
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
TQID: https://experienceleague.adobe.com/X1RtHTTmu0VIblFC3jANE7d6bIbtm4W5OvqFZDp8bLE
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
source-wordcount: 263
ht-degree: 90%

---

# 每次造訪逗留時間 (秒數)

*此說明頁面說明「每次造訪逗留時間」作為量度時的運作方式。 如需詳細資訊，請參閱[每次造訪逗留時間](../dimensions/time-spent-per-visit.md)維度。*

「每次造訪逗留時間（秒）」 [量度](overview.md)會顯示訪客在其各個造訪期間與指定維度專案互動的平均時間量。

由於處理架構不同，此量度在 Data Warehouse 中無法使用。

## 此量度的計算方式

此量度使用公式[`[Total seconds spent]`](total-seconds-spent.md)`divided by (`[`[Visits]`](visits.md)`minus`[`[Bounces]`](bounces.md)`)`。

## 與網站平均逗留時間比較

此量度與[網站平均逗留時間](average-time-on-site.md)類似，但有幾項主要差異。 這兩個量度都以「總逗留秒數」作為分子。 不過，「網站平均逗留時間」會以包含維度項目的序列作為分母。 每次造訪逗留時間會以造訪計數作為分母。

因此，這些量度在造訪層級會產生類似的結果，但在點擊層級就會有所差異。

## 高於 100% 的百分比

此量度常包含高於 100% 的百分比。 分母是整個維度的每次造訪逗留時間，分子是維度項目的每次造訪逗留時間。 如果整個維度的每次造訪逗留時間低於指定維度項目的每次造訪逗留時間，您就會看到高於 100% 的百分比。 依此量度排序的排名報表，會顯示異常的每次造訪逗留時間值，而這類值通常沒有價值。 Adobe 建議在排名報表中依其他量度　(例如[造訪](visits.md)) 進行排序。

如需更多關於逗留時間的一般資訊，請參閱[逗留時間概觀](time-spent.md)。

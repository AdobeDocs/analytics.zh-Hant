---
title: 平均工作階段長度 (行動)
description: 行動裝置的平均工作階段長度。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 41%

---

# 平均工作階段長度 (行動)

「平均工作階段長度（行動）」 [量度](overview.md) 顯示指定的維度專案存在於每個維度專案的平均時間量。 它類似於 [每次造訪逗留時間[秒]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) 量度，不過此量度會使用Mobile SDK特定元件進行計算。

## 此量度的計算方式

此量度使用[行動量度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hant)進行計算`'Total session length' / ('Launches' - 'First launches'`。

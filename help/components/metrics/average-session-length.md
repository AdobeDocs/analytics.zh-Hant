---
title: 平均工作階段長度 (行動)
description: 行動裝置的平均工作階段長度。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 29%

---

# 平均工作階段長度 (行動)

「平均工作階段長度（行動）」 [量度](overview.md)顯示指定的維度專案存在於每個維度專案的平均時間量。 此量度類似於[[!UICONTROL 每次造訪逗留時間（秒）]](time-spent-per-visit.md)量度，只是此量度使用行動SDK特定元件作為其計算的一部分。

## 此量度的計算方式

此量度是使用[生命週期量度](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`計算。

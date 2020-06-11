---
title: 平均工作階段長度 (行動)
description: 行動裝置的平均作業長度。
translation-type: tm+mt
source-git-commit: 625af73ad2fbe4b44bce00a122c4e65d8964323f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 9%

---


# 平均工作階段長度 (行動)

「平均作業長度（行動裝置）」量度顯示指定維度值在每個維度值中的平均呈現時間。 它類似於「網站平均 [逗留時間」度量](average-time-on-site.md) ，但此度量使用行動SDK特定元件作為其計算的一部分。

## 此度量的計算方式

此量度是使用行動量 [度計算](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html)`'Total session length' / ('Launches' - 'First launches'`。

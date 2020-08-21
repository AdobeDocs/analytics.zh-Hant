---
title: 平均工作階段長度 (行動)
description: 行動裝置的平均工作階段長度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 74%

---


# 平均工作階段長度 (行動)

「平均作業長度（行動裝置）」量度顯示指定維度項目在每個維度項目上的平均存在時間。 此量度類似於[網站平均逗留時間](average-time-on-site.md)量度，但會使用 Mobile SDK 特定元件進行計算。

## 此量度的計算方式

此量度使用[行動量度](https://docs.adobe.com/content/help/zh-Hant/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html)進行計算`'Total session length' / ('Launches' - 'First launches'`。

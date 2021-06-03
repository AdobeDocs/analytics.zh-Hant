---
title: 平均工作階段長度 (行動)
description: 行動裝置的平均工作階段長度。
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 90%

---

# 平均工作階段長度 (行動)

「平均工作階段長度 (行動)」量度會顯示指定維度項目的平均時間量以個別維度項目呈現。此量度類似於[網站平均逗留時間](average-time-on-site.md)量度，但會使用 Mobile SDK 特定元件進行計算。

## 此量度的計算方式

此量度使用[行動量度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html)進行計算`'Total session length' / ('Launches' - 'First launches'`。

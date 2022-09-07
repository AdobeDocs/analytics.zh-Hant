---
title: 平均工作階段長度 (行動)
description: 行動裝置的平均工作階段長度。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 47d5a532505aff48d43972836c78620870bd8221
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 65%

---

# 平均工作階段長度 (行動)

「平均工作階段長度 (行動)」量度會顯示指定維度項目的平均時間量以個別維度項目呈現。類似 [每次造訪逗留時間[秒]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) 量度，但此量度使用行動SDK特定元件進行計算。

## 此量度的計算方式

此量度使用[行動量度](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=zh-Hant)進行計算`'Total session length' / ('Launches' - 'First launches'`。

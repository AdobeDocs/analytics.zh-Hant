---
title: 平均工作階段長度 (行動)
description: 行動裝置的平均工作階段長度。
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
TQID: https://experienceleague.adobe.com/4TaQP7sH0pADpnwoQR-aqOpKqKvcuUXU1vmE3-ETOzM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 83
ht-degree: 36%

---

# 平均工作階段長度 (行動)

「平均工作階段長度（行動）」 [量度](overview.md)顯示指定的維度專案存在於每個維度專案的平均時間量。 此量度類似於[[!UICONTROL 每次造訪逗留時間（秒）]](time-spent-per-visit.md)量度，只是此量度使用行動SDK特定元件作為其計算的一部分。

## 此量度的計算方式

此量度是使用[生命週期量度](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`計算。

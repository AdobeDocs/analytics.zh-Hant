---
title: 分析行銷管道
description: 了解如何在工作區中使用行銷管道維度。
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
translation-type: tm+mt
source-git-commit: 9f978ecaa86eed450c80ab5a864f321b6223ba8c
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 90%

---

# 分析行銷管道

您可能想知道哪些行銷管道對什麼對象最有效，藉此讓行銷目標更為明確，並使付出的行銷資金獲得更高回報。在 Adobe Analytics 中，工作區裡的「行銷管道」維度和量度是能協助您追蹤不同管道對訂單、收入等之影響的其中一項工具，並能為您提供實用的管道分析。以下是您可使用的行銷管道相關維度與量度：

![](assets/mc-dims.png)

| 維度/量度 | 定義 |
| --- | --- |
| 行銷管道 | 這是我們建議使用的「行銷管道」維度。執行時，可將歸因 IQ 模型套用至此維度。此維度的運作方式與「上次接觸管道」維度相同，但標籤不同，這是為了避免在搭配不同歸因模型使用行銷管道時產生混淆。 |
| 上次接觸管道 | 舊版維度，已預先套用上次接觸歸因模型，且不可變更。 |
| 首次接觸管道 | 舊版維度，已預先套用首次接觸歸因模型，且不可變更。 |
| 行銷管道實例 | 此量度會測量行銷管道定義於影像要求中的次數，包括標準頁面檢視和自訂連結呼叫。不包含持續值。 |
| 新增參與 | 此量度類似於例項，但只有在影像要求中定義首次接觸行銷渠道時，此量度才會增加。 |

## 基本分析

此自由格式表格會顯示每個行銷管道的「線上訂單」、「線上收入」和「轉換率」量度：

![](assets/mc-viz1.png)

您可以在此在環圈圖中，看到每個行銷管道的「線上訂單」和「線上收入」：

![](assets/mc-viz2.png)

此線條圖會顯示各種管道之「線上訂單」隨時間變化的趨勢：

![](assets/mc-viz3.png)

## 進階分析

「行銷管道詳情」可深入分析每個管道，顯示特定的促銷活動、版位等。您可以劃分管道以便顯示詳情：

![](assets/mc-viz4.png)

## 套用歸因模型

您可以使用[歸因 IQ](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/panels/attribution/use-attribution.html)，即時套用不同的歸因模型：

![](assets/mc-viz5.png)

請留意在您套用不同歸因模型時，相同的量度 (「線上訂單」) 會如何產生不同結果。

## 跨標籤行銷分析

使用舊版「首次接觸渠道」和「上次接觸渠道」，您可以獲得渠道互動的有用視圖：

![](assets/mc-viz6.png)

了解更多關於視訊中的交叉標籤的行銷分析：[使用交叉標籤分析，探索 Analysis Workspace 內的基本行銷屬性](https://docs.adobe.com/content/help/zh-Hant/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html)。

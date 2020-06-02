---
title: 分析行銷管道
description: 了解如何在 Workspace 中使用行銷管道維度。
translation-type: tm+mt
source-git-commit: 586dabe8454bb2e6fbd4f3fbdb18d13a18b0417d
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 67%

---


# 分析行銷管道

您可能想知道哪些行銷管道對什麼對象最有效，藉此讓行銷目標更為明確，並使付出的行銷資金獲得更高回報。在Adobe Analytics中，工作區中的行銷管道維度和量度是可協助您追蹤不同管道對訂購、收入等的影響的工具之一。 並能為您提供實用的管道分析。以下是您可使用的行銷管道相關維度與量度：

![](assets/mc-dims.png)

| 維度/量度 | 定義 |
|---|---|
| 行銷管道 | 這是建議使用的行銷渠道維度。 執行時，可將歸因 IQ 模型套用至此維度。此維度的行為與「上次接觸渠道」維度相同，但標示不同，以防止與不同歸因模型搭配使用時混淆。 |
| 上次接觸管道 | 舊版維度，上次接觸歸因模型已預先套用且不可變更。 |
| 首次接觸管道 | 舊版維度，首次接觸歸因模型已預先套用且不可變更。 |
| 行銷管道實例 | 此度量會測量在影像請求中定義行銷渠道的次數，包括標準頁面檢視和自訂連結呼叫。 不包含持續值。 |
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

以下影片將詳細說明歸因 IQ：[歸因 IQ 播放清單](https://www.youtube.com/playlist?list=PL2tCx83mn7GuDzYEZ8jQlaScruZr3tBTR)。

## 跨標籤行銷分析

使用舊版「首次接觸管道」和「最後接觸管道」，即可檢視關於管道互動的實用資訊：

![](assets/mc-viz6.png)

透過[此影片](https://www.youtube.com/watch?v=M3EOdONa-3E)進一步了解跨標籤行銷分析。

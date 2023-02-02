---
title: 歸因最佳實務
description: 決定歸因模型的最佳實務為何？
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 58%

---

# 歸因最佳實務

為您的組織選擇正確的歸因模型取決於許多考量因素。 本文章探索方法及部分一般性最佳實務。

## 步驟 1：探索分析

>[!NOTE]
>選擇歸因模型前，必須進行此分析。

此階段包括在最初了解客戶行為，並定義轉換量度。 根據轉換量度，類似[資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=zh-Hant) (適用於原始資料) 或 Analysis Workspace 等工具有助於您了解

* 轉換前，接觸不同行銷管道的客戶人數
* 這些行為的比例/分佈

例如，如果 50% 的客戶在轉換前接觸 3 個管道，那麼在這 3 個管道中是否有任何互動？
您應該進行上層與下層漏斗分析，以擴大您的理解。

### 上層漏斗分析

漏斗上方分析管道可用來建立品牌或產品認知度。 例如，大多數電視廣告的目標是品牌知名度。 您可能會使用[「時間耗損」歸因模型](/help/analyze/analysis-workspace/attribution/models.md)，因為人們會隨著時間逐漸淡忘電視廣告。

### 下層漏斗分析

在漏斗較低的分析中，假設是人們已經知道您的品牌，而您希望他們轉換。 使用電子郵件、推播通知或Facebook廣告。

## 步驟 2：以規則為基礎的歸因

此步驟的目的是驗證您的假設。

**範例 1**

假設假設為：「我的首次接觸管道對轉換的影響比上次接觸管道大。」

在此情況下，您會使用 [「反向J形」歸因模型](/help/analyze/analysis-workspace/attribution/models.md) 來檢驗這個假設。 此模型將 60% 的功勞歸於首次接觸點。

**範例 2**

假設假設為：「在我們的行業（如旅遊行業），歸因期限是60天或90天，而不是30天，因為客戶在購買產品之前會做很多研究。」

在此情況下，您會將 [回顧期間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html#lookback-windows) 90天。

## 步驟 3：使用演算法歸因

如果您尚未建立歸因模型，可針對所有問題提供令人滿意的解答，您可以使用 [演算法歸因](/help/analyze/analysis-workspace/attribution/algorithmic.md). 由於很難驗證大量可能的假設和組合，演算法歸因會使用內建演算法，將評分分配給各個維度項目。

## 其他考量

* 您可能需要使用資料科學家的服務，而非僅仰賴 Analysis Workspace。
* 您可以仰賴原始資料，就像在 Adobe 資料摘要中一樣。
* 例如，如果您想要考量您的曝光數資料，可考慮使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html)。

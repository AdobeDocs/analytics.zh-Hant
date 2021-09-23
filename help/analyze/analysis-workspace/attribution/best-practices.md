---
title: 歸因最佳實務
description: 決定歸因模型的最佳實務為何？
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: e0a4caec9bc58a0846cd46871aad3bed99d218a3
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---

# 歸因最佳實務

為您的組織選擇正確的歸因模型取決於許多考量因素。 本文章探索方法及部分一般性最佳實務。

## 步驟 1：探索分析

>[!NOTE]
>選擇歸因模型前，必須進行此分析。

此階段包括在最初了解客戶行為，並定義轉換量度。 根據轉換量度，類似[資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) (適用於原始資料) 或 Analysis Workspace 等工具有助於您了解

* 有多少客戶在轉換前接觸不同的行銷通路？
* 這些行為的比例/分佈。

例如，如果 50% 的客戶在轉換前接觸 3 個管道，那麼在這 3 個管道中是否有任何互動？
您應該進行上層與下層漏斗分析，以擴大您的理解。

### 上層漏斗分析

上層漏斗分析會分析用於建立品牌或產品知名度的管道。 例如，大多數電視廣告的目標是品牌知名度。 您可能會使用[「時間耗損」歸因模型](/help/analyze/analysis-workspace/attribution/models.md)，因為人們會隨著時間逐漸淡忘電視廣告。

### 下層漏斗分析

在此分析中，假設人們已經知道您的品牌且您想要轉換。 使用電子郵件或推播通知或 Facebook 廣告。

## 步驟 2：以規則為基礎的歸因

此步驟的目的是驗證您的假設。

**範例 1**

假設您的假設如下：「我的首次接觸管道對轉換的影響力高於我的最終接觸管道」。 您之後會使用[「倒 J 形」歸因模型](/help/analyze/analysis-workspace/attribution/models.md)，以測試此假設。 此模型將 60% 的功勞歸於首次接觸點。

**範例 2**

您的假設可能是：「在我們的產業 (例如旅遊業)，歸因期間是 60 或 90 天，因為客戶在購買產品前會深入研究一番」。 您之後可能會將[回顧期間](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=en#lookback-windows)改成 90 天。

## 步驟 3：使用演算法歸因

由於很難驗證大量可能的假設及各種組合，因此您可以使用[演算法歸因](/help/analyze/analysis-workspace/attribution/algorithmic.md)，將此工作交由內建演算法進行。 如果您已找到解答您的所有問題且十分合適的完美歸因，那麼您顯然無需進行此步驟。

## 其他考量

* 您可能需要使用資料科學家的服務，而非僅仰賴 Analysis Workspace。
* 您可以仰賴原始資料，就像在 Adobe 資料摘要中一樣。
* 例如，如果您想要考量您的曝光數資料，可考慮使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en)。

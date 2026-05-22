---
title: 智慧型資料平滑
description: 瞭解智慧型資料平滑處理如何分析歷史趨勢，以預測受影響時段內任何量度的值。
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
TQID: 'https://experienceleague.adobe.com/iqjuEBGaCRcwmWfZo6rC1DXi8y4iyj9gB87tpvXmJdk'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b7156124-d291-4de4-ac0c-ed17d8078449
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 50f9ff18816ad88f231762b8b37c1ab9e1787b6f
workflow-type: tm+mt
source-wordcount: 256
ht-degree: 3%

---

# 智慧型資料平滑

在極少數情況下，某些因素會影響資料品質。 機器人流量、實作變更或服務中斷都可能影響所收集資料的完整性。 這些錯誤也會使分析事件如何影響資料完整性的工作複雜化。

智慧型資料平滑處理是[Analytics Labs](/help/analyze/labs.md)的原型，可分析歷史趨勢，預測受影響期間內任何量度的值，以協助完成此檢視。 原型會套用進階機器學習演演算法，以繪製所分析時段內量度的預期值。

## 執行智慧型資料平滑

1. 導覽至Adobe Analytics Labs：
   ![實驗室](assets/labs.png)
1. 啟動「智慧型資料平滑化」原型。
   ![啟動原型](assets/intelligent-ds.png)
1. 將必須分析的量度新增至自由表格。 原型僅適用於每日粒度，因此請確定表格中的維度為「日」。
   ![新增量度](assets/add-metric.png)
1. 選擇比事件視窗寬的日期範圍，但請確定該範圍包含事件。
   ![日期範圍](assets/date-range.png)
1. 按一下自由表格中量度的齒輪圖示。
   ![齒輪圖示](assets/gear-icon.png)
1. 在[!UICONTROL 資料設定]下，選取[!UICONTROL 資料平滑]選項。
   ![資料平滑](assets/column-setting.png)
1. 選取與事件對應的日期/日期範圍，然後按一下[!UICONTROL 套用]。
請確定「資料平滑」的資料範圍是為面板選取的資料範圍子集。 表格和圖表中的量度會被預測值取代。
   ![預測值](assets/predictive-values.png)

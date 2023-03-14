---
title: 智慧型資料平滑
description: 了解「智慧型資料平滑化」如何分析歷史趨勢，以預測受影響時段內任何量度的值。
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
source-git-commit: e0a4caec9bc58a0846cd46871aad3bed99d218a3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 4%

---

# 智慧型資料平滑

在某些罕見情況下，某些因素可能會影響資料品質。 機器人流量、實作變更或服務中斷都可能影響收集到資料的完整性。 這也會使有關事件如何影響資料完整性的分析變得複雜。

智慧資料平滑是 [Analytics Labs](/help/analyze/labs.md) 可分析歷史趨勢以預測受影響時段內任何量度的值，以協助完成此檢視。 原型會套用進階機器學習演算法，以繪製所分析時段內量度的預期值。

## 執行智慧資料平穩化

1. 導覽至Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. 啟動智慧資料平滑原型。
   ![Launch原型](assets/intelligent-ds.png)
1. 新增必須分析的量度至自由表格。 原型只適用於每日粒度，因此請確定表格中的維度為「日」。
   ![新增量度](assets/add-metric.png)
1. 選擇比事件視窗寬的日期範圍，但請確定包含事件。
   ![日期範圍](assets/date-range.png)
1. 在自由表格中按一下量度的齒輪圖示。
   ![齒輪表徵圖](assets/gear-icon.png)
1. 在 [!UICONTROL 資料設定]，請選取 [!UICONTROL 資料平穩化] 選項。
   ![資料平穩化](assets/column-setting.png)
1. 選取與事件對應的日期/日期範圍，然後按一下 [!UICONTROL 套用].
請確定「資料平滑化」的資料範圍是為面板選取之日期範圍的子集。 表格和圖表中的量度會由預測值取代。
   ![預計值](assets/predictive-values.png)

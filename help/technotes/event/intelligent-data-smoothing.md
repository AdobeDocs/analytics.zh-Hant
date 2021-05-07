---
title: 智慧型資料平滑
description: 瞭解智慧型資料平滑化如何分析歷史趨勢，以預測受影響時段內任何量度的值。
feature: AI 工具
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: aa9f0a8f5b7b1780d0b0be729775c573e12caa35
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 2%

---

# 智慧型資料平滑

在少數情況下，某些因素會影響資料品質。 機器人流量、實作變更或服務中斷都會影響所收集資料的完整性。 此外，它們也會使對事件如何影響資料完整性的分析變得複雜。

智慧型資料平滑化是[Analytics Labs](/help/analyze/tech-previews/overview.md)中的原型，可透過分析歷史趨勢來預測受影響時段內任何量度的值，協助完成此檢視。 原型會套用進階的機器學習演算法，以繪製在分析時段內量度的預期值。

## 執行智慧型資料平滑

1. 導覽至Adobe Analytics實驗室：
   ![Labs](assets/labs.png)
1. 啟動智慧型資料平滑原型。
   ![啟動原型](assets/intelligent-ds.png)
1. 新增必須分析的量度至自由表格。 原型僅適用於每日詳細程度，因此請確定表格中的維度為「日」。
   ![新增量度](assets/add-metric.png)
1. 選擇比事件視窗寬的日期範圍，但請確定包含事件。
   ![日期範圍](assets/date-range.png)
1. 按一下自由表格中量度的齒輪圖示。
   ![齒輪表徵圖](assets/gear-icon.png)
1. 在「[!UICONTROL 資料設定]」下方，選取「資料平滑]」選項。[!UICONTROL 
   ![資料平滑化](assets/column-setting.png)
1. 選擇與事件對應的日期／日期範圍，然後按一下[!UICONTROL 應用]。
請確定「資料平滑化」的資料範圍是面板所選日期範圍的子集。 表格和圖形中的度量會由預測值取代。
   ![預測值](assets/predictive-values.png)
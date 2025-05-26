---
description: 說明三種產品相容性選項。
title: 量度相容性
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: d9f95b12a43305cecff1190e6544334f3b48835d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 50%

---

# 量度相容性 {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="產品相容性"
>abstract="「少數可用的量度條件與所有Adobe Analytics工具不相容。 與量度相容的工具會在此清單中指明。 若要讓量度與所有Adobe Analytics工具相容，請嘗試編輯您的條件。"

本文說明三種產品相容性選項。

在計算量度產生器中建立計算量度時，您的量度會顯示為與Adobe Analytics中的一個或多個工具相容。 例如Analysis Workspace、Reports &amp; Analytics、Data Warehouse。


| 相容 | 說明 |
| --- | --- |
| 目前的資料 | Adobe Analytics 中的「[!UICONTROL 包含目前資料]」選項可讓您檢視最新 Analytics 資料，通常是在資料全部處理完並最終化之前。 「[!UICONTROL 目前資料]」會在數分鐘內顯示最多量度，進而提供可操作資料以幫助快速決策。 [!UICONTROL 目前的資料]僅支援計算量度（包含乘法、除法、加法和減法）。[!UICONTROL 目前的資料]不支援進階計算量度（包含區段或函式）。 |
| 完全處理的資料 | 已完全處理並包含區段和分類的資料。若您想在資料完全處理後檢視所有量度，則可將用戶從「目前資料用戶」群組中移除，以停用「[!UICONTROL 目前資料]」。 |
| 行銷管道報表 | 具有首次接觸配置的量度只與行銷管道報表相容。 |

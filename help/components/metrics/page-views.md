---
title: 頁面檢視次數
description: 維度項目的次數是設定或保存在 Adobe Analytics 中。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 100%

---

# 頁面檢視次數

**[!UICONTROL 頁面檢視次數]**[量度](overview.md)顯示特定維度項目在頁面上設定或持續存在的次數。這是報表中最常用且最基本的量度之一。

## 此量度的計算方式

此量度會計入報表套裝中的所有頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。維度包含維度項目被設定或持續存在的點擊次數。其中不包括連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 或來自[資料來源](/help/import/data-sources/overview.md)的資料。

## 與類似量度比較

* **頁面檢視次數與[造訪次數](visits.md)**：頁面檢視次數會計算頁面被檢視的次數。造訪次數會計算瀏覽者使用工作階段的數量。一次瀏覽包含一或多次頁面檢視。
* **頁面檢視次數與[頁面事件](page-events.md)**：頁面檢視次數會計算頁面檢視追蹤呼叫 (`t()`) 的數量，並排除連結追蹤呼叫 (`tl()`)。頁面事件次數正好反相；這類次數會計算連結追蹤呼叫的數量，並排除頁面檢視追蹤呼叫。

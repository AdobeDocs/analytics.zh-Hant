---
title: 頁面檢視次數
description: 維度項目的次數是設定或保存在 Adobe Analytics 中。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 51%

---

# 頁面檢視次數

**[!UICONTROL 頁面檢視次數]** [量度](overview.md)會顯示指定維度專案在頁面上設定或儲存的次數。 這是報表中最常用且最基本的量度之一。

## 此量度的計算方式

此量度會計入報表套裝中的所有頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。對於維度，其中包含已設定或儲存維度專案的點選。 其中不包含連結追蹤呼叫([`tl()`](/help/implement/vars/functions/tl-method.md))或來自[資料來源](/help/import/data-sources/overview.md)的資料。

## 與類似量度比較

* **頁面檢視與[造訪](visits.md)**&#x200B;的比較：頁面檢視會計算頁面被檢視的次數。 瀏覽次數會計算瀏覽者使用工作階段的數量。一次瀏覽包含一或多次頁面檢視。
* **頁面檢視與[頁面事件的比較](page-events.md)**：頁面檢視會計算頁面檢視追蹤呼叫(`t()`)的數量，並排除連結追蹤呼叫(`tl()`)。 頁面事件次數正好反相；這類次數會計算連結追蹤呼叫的數量，並排除頁面檢視追蹤呼叫。

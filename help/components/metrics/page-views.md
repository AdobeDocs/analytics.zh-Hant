---
title: 頁面檢視次數
description: 維度項目的次數是設定或保存在 Adobe Analytics 中。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: ht
source-wordcount: '197'
ht-degree: 100%

---

# 頁面檢視次數

**[!UICONTROL 頁面檢視次數]**&#x200B;量度顯示特定維度項在頁面上被定義或保留 (即過期時) 的次數。這是報表中最常用且最基本的量度之一。

例如，[!UICONTROL 一週中的幾天]量度由以下維度項組成：星期日、星期一、星期二、星期三、星期四、星期五和星期六。

## 此量度的計算方式

此量度會計入報表套裝中的所有頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。關於維度，這會包含已定義或保存的維度項目的點擊數。其中不包含連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 或[資料來源](/help/import/data-sources/overview.md)摘要中的資料。

## 與類似量度比較

* **頁面檢視次數與[瀏覽次數](visits.md)**：頁面檢視次數會計算頁面被檢視的次數。
瀏覽次數會計算瀏覽者使用工作階段的數量。一次瀏覽可包含一或多次頁面檢視。
* **頁面檢視次數與[頁面事件](page-events.md)**：頁面檢視次數會計算頁面檢視追蹤呼叫 (`t()`) 的數量，並排除連結追蹤呼叫 (`tl()`)。頁面事件次數正好反相；這類次數會計算連結追蹤呼叫的數量，並排除頁面檢視追蹤呼叫。

---
title: 頁面瀏覽數
description: 在Adobe Analytics設定或保留維項的次數。
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 65f87bf4b5b3897c9ef68d091858332c08cbf699
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 39%

---

# 頁面瀏覽數

「頁面檢視」量度會顯示指定維度項目在頁面上進行設定或保存的次數。這是報表中最常用且最基本的量度之一。

## 此量度的計算方式

此量度會計入報表套裝中的所有頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。對於維，它包括定義或保留維項的命中。 其中不包含連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 與類似量度比較

* **頁面視圖與 [訪問](visits.md)**:頁面視圖計數查看頁面的次數。 訪問會計訪問者的會話數。 一個訪問包含一個或多個頁面視圖。
* **頁面視圖與 [頁面事件](page-events.md)**:頁面視圖計數頁面視圖跟蹤調用數(`t()`)，並排除鏈路跟蹤呼叫(`tl()`)。 頁面事件正好相反；它們會計連結跟蹤調用的數量，並排除頁面視圖跟蹤調用。

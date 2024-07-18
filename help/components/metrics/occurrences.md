---
title: 發生次數
description: 變數經設定或持續存在的點擊次數。
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 100%

---

# 發生次數

「發生次數」[量度](overview.md)顯示點擊次數，其中會設定或保留指定的維度。當您將工作區中的維度拖曳至空白畫布時，Adobe 會自動將此量度套用至專案。

## 此量度的計算方式

在報告套裝中的所有點擊中，納入維度項目經定義或持續存在的點擊。有些維度 (例如 [eVar](../dimensions/evar.md)) 在其設定所在的點擊過後仍會持續存在。此量度會計算初始值和持續值。

## 與類似量度比較

* **發生次數與[例項](instances.md)**：發生次數會計入維度項目經設定或持續存在的點擊。例項不包含維度項目持續存在的點擊。
* **發生次數與[頁面檢視](page-views.md)**：發生次數包含所有點擊類型，包括頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))、連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md))，以及來自摘要[資料來源](/help/import/data-sources/overview.md)笉的資料。頁面檢視量度僅包括頁面檢視追蹤呼叫，不包括連結追蹤呼叫和摘要資料來源。

---
title: 發生次數
description: 變數經設定或持續存在的點擊次數。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 67%

---


# 發生次數

「發生次數」量度會顯示指定的維度經設定或持續存在的點擊次數。當您將工作區中的維度拖曳至空白畫布時，Adobe 會自動將此量度套用至專案。

## 此量度的計算方式

在報表套裝中的所有點擊中，包含定義或保留維度項目的點擊。 有些維度 (例如 [eVar](../dimensions/evar.md)) 在其設定所在的點擊過後仍會持續存在。此度量會計算初始值和持續值。

## 與類似量度比較

* **發生次數與例[項](instances.md)**:發生次數會計算設定或保存維度項目的點擊。 例項不包含維度項目持續存在的點擊。
* **發生次數與[頁面檢視](page-views.md)**：發生次數包含所有點擊類型，包括頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md)) 和連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md))。頁面檢視量度僅包含頁面檢視追蹤呼叫，而排除連結追蹤呼叫。

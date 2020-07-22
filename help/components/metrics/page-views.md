---
title: 頁面檢視
description: 頁面被檢視的次數。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 2%

---


# 頁面檢視

「頁面檢視」度量顯示指定維度項目在頁面上被設定或持續存在的次數。 這是報表中最常見和最基本的量度之一。

## 此度量的計算方式

此量度會計算報表套裝中的所[`t()`](/help/implement/vars/functions/t-method.md)有頁面檢視追蹤呼叫。 對於維度，它包含定義或保存維度項目的點擊。 它不包含連結追蹤呼叫([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 與類似度量比較

* **頁面檢視與瀏[覽](visits.md)**: 頁面檢視會計算頁面被檢視的次數。 瀏覽次數會計算訪客的工作階段數。 一次瀏覽包含一或多個頁面。
* **頁面檢視與頁[面事件](page-events.md)**: 頁面檢視會計算頁面檢視追蹤呼叫(`t()`)的數目，並排除連結追蹤呼叫(`tl()`)。 頁面事件則恰恰相反； 它會計算連結追蹤呼叫的數目，並排除頁面檢視。
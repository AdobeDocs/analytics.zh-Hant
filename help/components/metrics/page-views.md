---
title: '已說明的頁面檢視量度| Adobe Analytics '
description: 了解如何在 Adobe Analytics 中計算「頁面檢視」量度，並了解頁面檢視和造訪之間的區別。
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '176'
ht-degree: 100%

---

# 透過 Adobe Analytics 了解頁面檢視

「頁面檢視」量度會顯示指定維度項目在頁面上進行設定或保存的次數。這是報表中最常用且最基本的量度之一。

## 此量度的計算方式

此量度會計入報表套裝中的所有頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。對於維度，其中包含已定義或保存維度項目的點擊。其中不包含連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 與類似量度比較

* **頁面檢視與[造訪](visits.md)**&#x200B;的比較：頁面檢視會計算頁面被檢視的次數。「造訪」會計算訪客的工作階段數量。一次造訪包含一或多個頁面。
* **頁面檢視與[頁面事件](page-events.md)**&#x200B;的比較：頁面檢視會計算頁面檢視追蹤呼叫 (`t()`) 的數量，並排除連結追蹤呼叫 (`tl()`)。頁面事件則相反；它會計算連結追蹤呼叫的數量，而排除頁面檢視。

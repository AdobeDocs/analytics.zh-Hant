---
title: '說明頁面檢視量度 | Adobe Analytics '
description: 瞭解Adobe Analytics中如何設計頁面檢視度量，並瞭解頁面檢視與瀏覽之間的差異。
translation-type: tm+mt
source-git-commit: c588087b949093152435967f62e43758e9e86208
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 80%

---


# 瞭解使用Adobe Analytics進行頁面檢視

「頁面檢視」量度會顯示指定維度項目在頁面上進行設定或保存的次數。這是報表中最常用且最基本的量度之一。

## 此量度的計算方式

此量度會計入報表套裝中的所有頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。對於維度，其中包含已定義或保存維度項目的點擊。其中不包含連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md))。

## 與類似量度比較

* **頁面檢視與[造訪](visits.md)**&#x200B;的比較：頁面檢視會計算頁面被檢視的次數。「造訪」會計算訪客的工作階段數量。一次造訪包含一或多個頁面。
* **頁面檢視與[頁面事件](page-events.md)**&#x200B;的比較：頁面檢視會計算頁面檢視追蹤呼叫 (`t()`) 的數量，並排除連結追蹤呼叫 (`tl()`)。頁面事件則相反；它會計算連結追蹤呼叫的數量，而排除頁面檢視。
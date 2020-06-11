---
title: 頁面事件
description: 觸發的連結追蹤動作數。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# 頁面事件

「頁面事件」量度顯示任何連結追蹤呼叫的發生次數。 當您想要瞭解哪些頁面擁有最吸引人的內容時，此度量會很有幫助。 當訪客可以在頁面上執行動作，而不導覽至新頁面時，此度量的測量最有價值。

## 此度量的計算方式

此度量會計算報表套裝中的所[`tl()`](/help/implement/vars/functions/tl-method.md)有連結追蹤呼叫()。 包含所有連結類型（自訂連結、下載連結和退出連結）。 它不包含頁面檢視追蹤呼叫([`t()`](/help/implement/vars/functions/t-method.md))。

## 與類似度量比較

* **頁面事件與頁[面檢視](page-views.md)**: 頁面事件會計算連結追蹤追蹤呼叫(`tl()`)的數目，並排除頁面檢視追蹤呼叫(`t()`)。 頁面檢視則相反； 它會計算頁面檢視追蹤呼叫的數目，並排除連結。

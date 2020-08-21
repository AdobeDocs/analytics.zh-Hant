---
title: 頁面事件
description: 連結追蹤動作的觸發次數。
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---


# 頁面事件

「頁面事件」量度會顯示任何連結追蹤呼叫的執行次數。如果您想要瞭解哪些頁面具有最吸引人的內容，此量度將有所幫助。當訪客無須導覽至新頁面即可在頁面上執行動作時，此量度的測量尤有效益。

## 此量度的計算方式

此量度會計算報表套裝中的所有連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md))。其中包括所有的連結類型 (自訂連結、下載連結和退出連結)。但不含頁面檢視追蹤呼叫 ([`t()`](/help/implement/vars/functions/t-method.md))。

## 與類似量度比較

* **頁面事件與[頁面檢視](page-views.md)**&#x200B;的比較：頁面事件會計算連結追蹤呼叫 (`tl()`) 的數量，並排除頁面檢視追蹤呼叫 (`t()`)。頁面檢視則相反；它會計算頁面檢視追蹤呼叫的數量，並排除連結。

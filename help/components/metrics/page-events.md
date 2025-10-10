---
title: 頁面事件
description: 連結追蹤動作的觸發次數。
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 205d86b13046bd17e321734904bf57435ef6e106
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 33%

---

# 頁面事件

「頁面事件」 [量度](overview.md)會顯示任何連結追蹤呼叫的執行次數。 如果您想要瞭解哪些頁面具有最吸引人的內容，此量度將有所幫助。當訪客無須導覽至新頁面即可在頁面上執行動作時，此量度的測量尤有效益。

例如，在電子商務網站的典型歷程中，訪客可在單一頁面上進行數個互動。 典型的Analytics實作將這些互動設定為連結追蹤([`tl()`](/help/implement/vars/functions/tl-method.md))呼叫，而頁面檢視([`t()`](/help/implement/vars/functions/t-method.md))呼叫則保留給初始頁面載入。 此實作方法提供豐富的事件追蹤功能，可針對insight在訪客繼續其歷程之前發生的互動提供資訊。

## 此量度的計算方式

此量度會計算報表套裝中的所有連結追蹤呼叫 ([`tl()`](/help/implement/vars/functions/tl-method.md))。此量度包含所有連結型別，尤其是[自訂連結](../dimensions/custom-link.md)、[下載連結](../dimensions/download-link.md)和[退出連結](../dimensions/exit-link.md)。 它不包含頁面檢視呼叫([`t()`](/help/implement/vars/functions/t-method.md))。

## 與類似量度比較

* **頁面事件與[頁面檢視](page-views.md)**&#x200B;的比較：頁面事件會計算連結追蹤呼叫([`tl()`](/help/implement/vars/functions/tl-method.md))的數量，並排除頁面檢視追蹤呼叫([`t()`](/help/implement/vars/functions/t-method.md))。 頁面檢視則相反；它會計算頁面檢視追蹤呼叫的數量，並排除連結。

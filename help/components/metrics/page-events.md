---
title: 頁面事件
description: 連結追蹤動作的觸發次數。
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: a7434f72159a575f9ad7bf29644cb17777382df7
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 40%

---

# 頁面事件

「頁面事件」 [量度](overview.md) 顯示任何連結追蹤呼叫的執行次數。 如果您想要瞭解哪些頁面具有最吸引人的內容，此量度將有所幫助。當訪客無須導覽至新頁面即可在頁面上執行動作時，此量度的測量尤有效益。

## 此量度的計算方式

此量度會計入全部 [連結追蹤呼叫(`tl()`)](/help/implement/vars/functions/tl-method.md) 報表套裝中的。 此量度包含所有連結型別，尤其是 [自訂連結](../dimensions/custom-link.md)， [下載連結](../dimensions/download-link.md)、和 [退出連結](../dimensions/exit-link.md). 不包括 [頁面檢視追蹤呼叫(`t()`)](/help/implement/vars/functions/t-method.md).

## 與類似量度比較

* **頁面事件與 [頁面檢視](page-views.md)**：頁面事件會計算連結追蹤呼叫的數量(`tl()`)和排除頁面檢視追蹤呼叫(`t()`)。 頁面檢視則相反；它會計算頁面檢視追蹤呼叫的數量，並排除連結。

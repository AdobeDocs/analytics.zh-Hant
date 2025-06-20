---
description: 顯示篩選和加權量度的範例。
title: 篩選和加權量度
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 89%

---

# 篩選和加權量度

本文示範篩選和加權量度的範例。

## 已篩選的反彈率

這個簡單的已篩選量度只顯示超過 100 次瀏覽之頁面的反彈率：

![篩選的跳出率](assets/filtered-bounce-rate.png){zoomable="yes"}

請記住，此公式相依於一致的時間範圍。如果您針對單日執行報表，則超過 20 次瀏覽的頁面都值得查看。如果您針對一個月執行報表，可能會想讓篩選包含更多次瀏覽。

## 使用百分位數篩選的反彈率

依瀏覽次數排序時，此篩選器會顯示前 30% 頁面的反彈率。

![使用百分位數](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}篩選的跳出率

## 加權量度

假設您想在一般情形下依反彈率排序，但瀏覽次數較高的頁面應排在清單中較前面的位置。那麼您應建立加權的反彈率，如下所示：

![](assets/weighted-bounce-rate.png)

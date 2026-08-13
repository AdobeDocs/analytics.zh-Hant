---
description: 瞭解篩選和加權量度的範例。
title: 篩選和加權量度
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
TQID: https://experienceleague.adobe.com/Euk3sI0-AYtfmpEbL-8gfWU4HcFE6kGO6QGgctZbvig
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 19%

---

# 篩選和加權的量度

本文示範篩選和加權量度的範例。

## 篩選的跳出率

這個簡單的已篩選量度只顯示超過 100 次瀏覽之頁面的反彈率：

![篩選的跳出率](assets/filtered-bounce-rate.png){zoomable="yes"}

請記住，此公式相依於一致的時間範圍。 如果您執行一天報表，則任何超過20次瀏覽的頁面都值得一看。 如果您將其執行一個月，則可能會希望篩選器包含更多造訪。

## 使用百分位數的篩選跳出率

此篩選器在依瀏覽次數排序時，會顯示前30%頁面的跳出率。

![使用百分位數](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}篩選的跳出率

## 加權跳出率

假設您一般想要依跳出率排序，但瀏覽次數較高的頁面在清單中應比較高。 那麼您應建立加權的反彈率，如下所示：

![](assets/weighted-bounce-rate.png)

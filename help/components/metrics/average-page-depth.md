---
title: 平均頁面深度
description: 維度平均存在於多少頁面的深度中。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 59%

---


# 平均頁面深度

「平均頁面深度」量度會顯示維度項目在指定瀏覽中的距離。 例如，假設您的首頁通常會顯示比購買確認頁面小的平均頁面深度，而購買確認頁面通常會在造訪中的較深之處。當您想要瞭解指定維度項目中平均有多少頁面時，此度量會很有幫助。 如果特定頁面的平均深度較低，您可使用這項資訊為新訪客最佳化這些頁面。

>[提示]：將此量度與其他量度 (例如[造訪](visits.md)) 搭配使用，有助於進行深入分析。如果您單獨使用此量度，您會取得包含異常頁面深度的維度項目，這通常不有價值。

## 此量度的計算方式

造訪的第一個頁面具有頁面深度 `0`。下一個頁面的頁面深度為 1，且會隨著每個頁面檢視而遞增，直到造訪結束為止。此量度只會隨著頁面檢視 ([`t()`](/help/implement/vars/functions/t-method.md)) 呼叫而增加，而不會隨著連結追蹤 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 呼叫而增加。

對於指定的維度項目，請新增該維度項目的所有頁面深度，並依瀏覽次數加以劃分。 產生的數字即為平均頁面深度，會捨入進位至最接近的整數。Dimension items with an average page depth of `0` means it was frequently on the first page of the visit.

例如，請考量下列範例造訪：

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

If we wanted average page depth for the dimension item `Page2`, it would be calculated as follows:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>如果您想看到具有小數位數的平均頁面深度，請建立計算量度，並以此量度作為公式中的唯一元素。將計算量度中的小數位數增加至所需的小數。

## 高於 100% 的百分比

此量度常包含高於 100% 的百分比。分母是整個維度的平均頁面深度，分子是維度項目的平均頁面深度。 如果整個維度的平均頁面深度低於指定維度項目的平均頁面深度，您會看到超過100%的百分比。 依此量度排序的排名報表，會顯示異常的平均頁面深度值，而這類值通常沒有價值。Adobe 建議在排名報表中依其他量度　(例如[造訪](visits.md)) 進行排序。
---
title: 平均頁面深度
description: 維度平均存在於多少頁面的深度中。
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 96%

---


# 平均頁面深度

「平均頁面深度」量度會顯示維度項目在指定造訪中的深入程度。例如，假設您的首頁通常會顯示比購買確認頁面小的平均頁面深度，而購買確認頁面通常會在造訪中的較深之處。如果您想要了解指定的維度項目平均存在於多少頁面的深度中，此量度將有所幫助。如果特定頁面的平均深度較低，您可使用這項資訊為新訪客最佳化這些頁面。

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. 如果單獨使用此量度，您的維度項目將會包含異常的頁面深度，而這類項目通常不實用。

## 此量度的計算方式

造訪的第一個頁面具有頁面深度 `0`。下一個頁面的頁面深度為 1，且會隨著每個頁面檢視而遞增，直到造訪結束為止。此量度只會隨著頁面檢視 ([`t()`](/help/implement/vars/functions/t-method.md)) 呼叫而增加，而不會隨著連結追蹤 ([`tl()`](/help/implement/vars/functions/tl-method.md)) 呼叫而增加。

針對指定的維度項目，加總該維度項目的所有頁面深度，然後將其除以造訪次數。產生的數字即為平均頁面深度，會捨入進位至最接近的整數。維度項目的平均頁面深度若為 `0`，表示它經常出現在造訪的第一個頁面。

例如，請考量下列範例造訪：

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

如果我們想求出維度項目 `Page2` 的平均頁面深度，其計算方式如下：

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

此量度常包含高於 100% 的百分比。分母是整個維度的平均頁面深度，分子是維度項目的平均頁面檢視深度。如果整個維度的平均頁面深度低於指定維度項目的平均頁面深度，您就會看到高於 100% 的百分比。依此量度排序的排名報表，會顯示異常的平均頁面深度值，而這類值通常沒有價值。Adobe 建議在排名報表中依其他量度　(例如[造訪](visits.md)) 進行排序。
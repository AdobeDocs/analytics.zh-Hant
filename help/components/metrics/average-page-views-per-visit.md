---
title: 每次造訪的平均頁面瀏覽數
description: 指定的維度項目出現在造訪中的平均次數。
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
TQID: https://experienceleague.adobe.com/sospsPhk77O5qOLcMLmu7gB7rvlxbp8rGqB39LCnQ5g
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 92%

---

# 每次造訪的平均頁面瀏覽數

「每次造訪的平均頁面檢視」維度會顯示對您所需的維度發生的平均頁面檢視次數。 對於以時間為基礎的維度，您可以瞭解造訪中的平均頁面檢視次數在一段時間內的趨勢。 如果您想要瞭解維度專案在造訪中的出現頻率，此[量度](overview.md)將有所幫助。

>[!TIP]
>
>將此量度與其他量度 (例如[瀏覽次數](visits.md)) 搭配使用，有助於進行洞察。 如果單獨使用此量度，您的維度項目將會包含異常的每次造訪頁面檢視次數，而這類值通常不實用。

## 此量度的計算方式

此量度的計算公式為 [`Page views`](page-views.md)` divided by `[`Visits`](visits.md)。

## 高於 100% 的百分比

此量度常包含高於 100% 的百分比。 分母是整個維度的每次造訪平均頁面檢視次數，分子是維度項目的每次造訪平均頁面檢視次數。 如果整個維度的每次造訪平均頁面檢視次數低於指定維度項目的每次造訪平均頁面檢視次數，您就會看到高於 100% 的百分比。 依此量度排序的排名報表，會顯示異常的「每次造訪的平均頁面檢視」值，而這類值通常沒有價值。 Adobe 建議在排名報表中依其他量度 (例如[造訪](visits.md)) 進行排序。

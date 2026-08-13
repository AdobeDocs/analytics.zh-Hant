---
description: 瞭解依量度排序如何讓Data Warehouse報表易於解譯，並與其他Analytics劃分報表檢視進行比較。
title: 依量度排序
feature: Data Warehouse
exl-id: 6bd82951-c3b4-4ba2-8e4d-b7c9b351911b
TQID: 'https://experienceleague.adobe.com/YPqL6i9RWACubLdf2ywm8xuPyeQkZ30L6rO6FAbhpJI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 337
ht-degree: 17%

---

# 依量度排序

在Data Warehouse中提供依遞減量度值排序的排名劃分報表。

依量度排序可讓您更輕鬆地解讀Data Warehouse報表，並讓這些報表更易於與其他Analytics劃分報表檢視進行比較。

以下說明啟用「量度排序」選項後，Data Warehouse報表中的列會如何重新排序。

根據日期詳細程度、報表維度或量度的設定方式，以及是否設定「最大列數」，Data Warehouse報表的組織「量度排序」有四種可能方式：

* **版面配置1**：條列專案會依字典順序排序（預設）。 如果設定「最大列數」，則報表中僅會提供前N列。
* **配置 2**：Data Warehouse 對報表中的所有列套用量度排序。 第一個量度值中的繫結會依第2個量度劃分，接著再依第3個量度劃分，依此類推。 繫結所有量度時，會套用劃分條列專案的標準字典順序。
* **配置3**：作為「配置2」，只有前N列（亦即「最大列」中設定的數字）會輸出在報表中。
* **配置4**：以配置2的形式，但每個日期粒度期間的行專案會分組在一起，並在各自的時間範圍內排序。

請參考此表格中的「報表配置」欄，以決定「量度排序」與其他Data Warehouse報表選項的互動方式。

| 依量度排序? | 有量度嗎？ | 有劃分嗎？ | 日期粒度？ | 設定的列數上限？ | 報告配置 |
|---|---|---|---|---|---|
| 無 | 「是」或「否」 | 「是」或「否」 | 「是」或「否」 | 「是」或「否」 | 1 |
| 是 | 無 | 「是」或「否」 | 「是」或「否」 | 「是」或「否」 | 1 |
| 是 | 是 | 無 | 否 | 不適用 | 1 |
| 是 | 是 | 無 | 「是」或「否」 | 無 | 1 |
| 是 | 是 | 是 | 無 | 否 | 2 |
| 是 | 是 | 無 | 是 | 是 | 3 |
| 是 | 是 | 是 | 「是」或「否」 | 是 | 3 |
| 是 | 是 | 是 | 是 | 無 | 4 |

---
title: 搜尋
description: 點擊符合外部搜尋條件的次數。
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
TQID: https://experienceleague.adobe.com/bcK-h9tkOKRHFoZ5EbX05ppNtV5S8Kok8dhMJZxf-ao
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 88%

---

# 搜尋

「搜尋」[量度](overview.md)會顯示符合Adobe外部搜尋偵測的點選數。 如果您想要查看非搜尋維度項目，並了解它們對搜尋引擎流量的貢獻，此量度就十分實用。

## 此量度的計算方式

此量度會計算符合 Adobe 外部搜尋偵測的點擊次數。 它必須符合以下兩個條件：

* 點擊的反向連結值是 Adobe 認可的搜尋網域
* 點擊的反向連結 URL 包含關鍵字查詢字串參數。 由於現今的隱私權實務趨於嚴謹，此查詢字串值通常為空白。 Adobe 會將空白的關鍵字查詢字串辨識為搜尋偵測的一部分。

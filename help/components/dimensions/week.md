---
title: 週
description: 量度發生的週別。
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
TQID: https://experienceleague.adobe.com/Vvr0Svg2khSzWbtWR5hLfveyctOEM-62WU6oxIsvzXs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 92%

---

# 週

「週」[維度](overview.md)會報告指定量度發生的周。 第一個維度項目是日期範圍中的第一週，最後一個維度項目是日期範圍中的最後一週。 此維度可讓您查看量度在一段時間內變化，因此對趨勢報表而言十分重要。

## 將資料填入此維度中

此維度可直接用於所有實施作業。 如果報告套裝包含資料，此維度即會運作。

## 維度項目

在 Analysis Workspace 中，維度項目包括一週中第一天的日期 (月、日和年)。

在 Data Warehouse，維度項目會根據請求的日期範圍納入有編號的週。 例如，第一個完整週是 `"Week 1"`。 如果請求包含一週的一部分，資料會分組到維度項目 `"Week 0"`。

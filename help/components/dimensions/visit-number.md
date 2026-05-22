---
title: 造訪次數
description: 訪客的第 n 次造訪。
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
TQID: https://experienceleague.adobe.com/C6fccfJFGSA4iLuhp2X80aPym4ZcwbrLMaUS2LUfosg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 100%

---

# 造訪次數

「造訪次數」[維度](overview.md)是報告訪客目前所在的造訪情形。 新的造訪開始時，此維度項目會加 1。 如果您想要瞭解參與的訪客回訪網站時的情況，此維度將有所幫助。 這是以造訪為基礎的維度，這表示其中包含整個造訪共同的值，且無法變更。 此維度會套用至訪客的存留期，無論專案日期範圍為何。

## 將資料填入此維度中

此維度可直接用於所有實施作業。 如果報告套裝包含資料，此維度即會運作。

## 維度項目

維度項目包含字串 `"Visit number"`，及其後面代表訪客目前所在之造訪的數值。 例如，如果訪客以前從未造訪過您的網站，則其首次造訪屬於維度項目 `"Visit number 1"`。 如果這是訪客對您的網站第 13 次的造訪，則屬於維度項目 `"Visit number 13"`。

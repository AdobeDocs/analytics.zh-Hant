---
title: 色彩深度
description: 裝置的色彩深度。
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 94%

---

# 色彩深度

「色彩深度」[維度](overview.md)會報告裝置支援的色彩數量。 此維度可用來判斷有多少流量源自不支援 1600 萬色的裝置。 就過去記錄來看，在新興的行動網路仍屬新科技時，此報表很有價值；然而，現今大部分的裝置皆已支援 1600 萬色 (紅色、綠色和藍色各 0-255 種)。<!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## 將資料填入此維度中

此維度會參考查閱表格，將位元值轉換為更易讀的格式。 它會從影像要求中的 [`c` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。 AppMeasurement 會使用 `screen.colorDepth` 變數填入影像要求查詢字串。 如果您使用 AppMeasurement (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在具有有效位元值的每個點擊上包含 `c` 查詢字串參數。

## 維度項目

維度項目包含裝置支援的色彩數量。 範例值包括 `"16 million (24-bit)"`、`"16 million (32-bit)"` 和 `"65,536 (16-bit)"`。 如果 AppMeasurement 無法判斷色彩深度，則會顯示為 `"None"`。

>[!TIP]
>
>24 位元和 32 位元支援的區別在於 32 位元支援 alpha 色版 (RGBA)，而 24 位元則不支援 (RGB)。 如需此概念的詳細資訊，請參閱 Wikipedia 上的[色彩深度](https://en.wikipedia.org/wiki/Color_depth)。

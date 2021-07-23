---
title: 色彩深度
description: 裝置的色彩深度。
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 色彩深度

「色彩深度」維度會報告裝置支援的色彩數量。此維度可用來判斷有多少流量源自不支援 1600 萬色的裝置。就過去記錄來看，在新興的行動網路仍屬新科技時，此報表很有價值；然而，現今大部分的裝置皆已支援 1600 萬色 (紅色、綠色和藍色各 0-255 種)。<!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## 將資料填入此維度中

此維度會參考查閱表格，將位元值轉換為更易讀的格式。它會從影像要求中的 [`c` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。AppMeasurement 會使用 `screen.colorDepth` 變數填入影像要求查詢字串。如果您使用AppMeasurement(例如透過Adobe Experience Platform中的標籤)，此維度會立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在具有有效位元值的每次點擊上包含 `c` 查詢字串參數。

## 維度項目

維度項目包含裝置支援的色彩數量。範例值包括 `"16 million (24-bit)"`、`"16 million (32-bit)"` 和 `"65,536 (16-bit)"`。如果 AppMeasurement 無法判斷色彩深度，則會顯示為 `"None"`。

>[!TIP]
>
>24 位元和 32 位元支援的區別在於 32 位元支援 alpha 色版 (RGBA)，而 24 位元則不支援 (RGB)。如需此概念的詳細資訊，請參閱 Wikipedia 上的[色彩深度](https://en.wikipedia.org/wiki/Color_depth)。

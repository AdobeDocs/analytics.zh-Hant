---
title: 色彩深度
description: 裝置的色深。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# 色彩深度

「色彩深度」維度會報告裝置支援的色彩數量。 此維度可用來判斷有多少流量源自不支援1600萬色的裝置。 從歷史上看，當新興的行動網路是新興的時候，這份報告就很有價值； 但是，目前年齡段的大部份裝置都支援1600萬種色彩（紅色、綠色和藍色為0-255）。 <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## 將資料填入此維度

此維度會參考查閱表格，將位元值轉換為更易讀的格式。 它會從影像請求中 [`c` 的查詢字串](/help/implement/validate/query-parameters.md) 收集資料。 AppMeasurement使用變 `screen.colorDepth` 數來填入影像請求查詢字串。 如果您使用AppMeasurement（例如透過Adobe Experience Platform Launch），此維度將立即可用。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在每個點擊上加入具有有效位元值的查詢字串參數。 `c`

## 維度項目

維度項目包括裝置支援的色彩數目。 範例值 `"16 million (24-bit)"`包括、 `"16 million (32-bit)"`和 `"65,536 (16-bit)"`。 如果AppMeasurement無法判斷色彩深度，則會顯示為 `"None"`。

>[!TIP]
>
>24位元和32位元支援的區別在於32位元支援alpha色版(RGBA)，而24位元則不支援(RGB)。 如需 [此概念的詳細資訊](https://en.wikipedia.org/wiki/Color_depth) ，請參閱Wikipedia的色彩深度。

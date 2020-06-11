---
title: 瀏覽深度
description: 報告瀏覽深度的瀏覽型維度。
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# 瀏覽深度

「瀏覽深度」維度會報告訪客在整個瀏覽中檢視的頁面檢視次數。 瀏覽深度只會在點擊為頁面檢視，且 [Page](page.md) （頁面）維度與最後一個頁面檢視的維度值不同時，才會增加。 此維度是以瀏覽為基礎的維度，表示其包含的值與整個瀏覽的值相同。 此變數會針對該次瀏覽結束後的瀏覽中的所有點擊設定。

## 將資料填入此維度

此維度適用於所有實作，不需開箱即用。 如果報表套裝包含資料，此維度會運作。

## 維度值

維度值包括字 `"Pages per visit"` 串，後面接著代表瀏覽中頁數的數字。 維度值代 `"Pages per visit: 1"` 表單頁瀏覽，而維度值代 `"Pages per visit: 8"` 表具有8個頁面檢視（以及任何數目的連結追蹤呼叫）的瀏覽。

## 點擊深度比較

如需 [維度間的比較](hit-depth.md) ，請參閱「點擊深度」。
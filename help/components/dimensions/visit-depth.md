---
title: 造訪深度
description: 報告造訪深度的造訪相關維度。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 57%

---


# 造訪深度

「造訪深度」維度會報告訪客在整個造訪中瀏覽的頁面檢視次數。Visit depth increases only if the hit is a page view, and the [Page](page.md) dimension is not the same as the last page view&#39;s dimension item. 這是以造訪為基礎的維度，這表示其中包含整個造訪共同的值。此變數的設定範圍，涵蓋某個造訪結束後的所有點擊。

## 將資料填入此維度中

此維度可直接用於所有實作。如果報表套裝包含資料，此維度即會運作。

## 維度項目

Dimension items include the string `"Pages per visit"` followed by a number representing the number of pages in the visit. The dimension item of `"Pages per visit: 1"` represents a single-page visit, while the dimension item `"Pages per visit: 8"` represents a visit with 8 page views (and any number of link tracking calls).

## 與點擊深度比較

如需維度之間的比較，請參閱[點擊深度](hit-depth.md)。
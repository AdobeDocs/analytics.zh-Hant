---
title: 造訪次數
description: 訪客的第 n 次造訪。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 59%

---


# 造訪次數

「造訪次數」維度會報告訪客目前所在的造訪。當新瀏覽開始時，此維度項目會增加1。 如果您想要瞭解參與的訪客回訪網站時的情況，此維度將有所幫助。這是以造訪為基礎的維度，這表示其中包含整個造訪共同的值，且無法變更。此維度會套用至訪客的存留期，無論專案日期範圍為何。

## 將資料填入此維度中

此維度可直接用於所有實作。如果報表套裝包含資料，此維度即會運作。

## 維度項目

Dimension items include the string `"Visit number"` followed by the numeric representation of the visit the visitor is currently on. For example, if the visitor has never been to your site before, their first visit belongs to the dimension item `"Visit number 1"`. If this is the visitor&#39;s 13th visit to your site, they belong to the dimension item `"Visit number 13"`.

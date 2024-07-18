---
title: 監視器解析度
description: 訪客螢幕的解析度 (以像素為單位)。
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 93%

---

# 監視器解析度

「監視器解析度」[維度](overview.md)以畫素顯示使用中顯示器的高度和寬度。 若您想了解網站上的「折頁」在什麼位置向訪客顯示，或是訪客瀏覽器視窗的寬度，這個維度相當實用。瞭解折頁的位置可讓您將內容最佳化以供檢視。

此維度與瀏覽器高度和寬度不同。瀏覽器高度/寬度是可檢視瀏覽器空間內的像素數，而螢幕解析度是整個螢幕的像素數。如果您想在自己的電腦上觀察這兩個變數之間的差異，請開啟瀏覽器主控台 (在大部分的瀏覽器上為 F12)，並將下列程式碼複製並貼到主控台中：

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

瀏覽器維度一律小於螢幕解析度，因為瀏覽器維度不包含瀏覽器導覽區或邊界。

## 將資料填入此維度中

此維度會從影像要求中的 [`s` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 JavaScript 變數 `screen.width` 和 `screen.height` 在瀏覽器中收集這項資料。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在影像要求中包含 `s` 查詢字串參數。

## 維度項目

維度項目包含所有收集的螢幕解析度。範例值包括 `1920 x 1080`、`1366 x 768` 和 `1280 x 720`。

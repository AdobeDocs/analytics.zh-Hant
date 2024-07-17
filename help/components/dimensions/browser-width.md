---
title: 瀏覽器寬度 - 分段
description: 瀏覽器視窗的寬度 (像素)。
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
source-git-commit: 2601b0e5c3fa78237ce693801b8dd8c95b853b81
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 81%

---

# 瀏覽器寬度

「瀏覽器寬度 — 分段」[維度](overview.md)會顯示瀏覽器視窗的寬度，並將其分類為預先定義的群組。 如果您想要瞭解訪客以何種寬度範圍檢視您的內容，此維度就十分實用。瞭解您通常在中檢視內容的寬度，可讓您將內容最佳化。

此維度與熒幕寬度不同。 瀏覽器寬度是可檢視瀏覽器空間內的像素數，而螢幕寬度則是整個監視器的寬度 (像素)。如果您想在自己的電腦上觀察這兩個變數之間的差異，請開啟瀏覽器主控台 (在大部分的瀏覽器上為 F12)，並將下列程式碼複製並貼到主控台中：

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

瀏覽器寬度一律小於或等於螢幕寬度，因為瀏覽器寬度不包含捲軸或邊界。

## 將資料填入此維度中

此維度會從影像要求中的 [`bw` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 JavaScript 變數 `window.innerWidth` 在瀏覽器中收集這項資料。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在每次造訪的第一次點擊上包含 `bw` 查詢字串參數。

Adobe 會在造訪期間保存瀏覽器寬度。如果瀏覽器寬度在造訪期間有所調整，將不會記錄該調整。

## 維度項目

Dimension專案包含所有收集到的瀏覽器寬度，並歸類到預先定義的群組中。 例如，如果點擊的瀏覽器寬度為 `1280`，則會將其歸類到維度項目 `1200 to 1299` 中。

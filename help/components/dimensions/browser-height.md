---
title: 瀏覽器高度 - 分段
description: 瀏覽器視窗的高度 (像素)。
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
source-git-commit: 2601b0e5c3fa78237ce693801b8dd8c95b853b81
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 87%

---

# 瀏覽器高度

「瀏覽器高度 — 分段」[維度](overview.md)會顯示瀏覽器視窗的高度，並將其分類為預先定義的群組。 如果您想要瞭解訪客在您網站上的「折頁」位置，此維度就十分實用。瞭解折頁的位置可讓您將內容最佳化以供檢視。

此維度與熒幕高度不同。 瀏覽器高度是可檢視瀏覽器空間內的像素數，而螢幕高度則是整個監視器的高度 (像素)。如果您想在自己的電腦上觀察這兩個變數之間的差異，請開啟瀏覽器主控台 (在大部分的瀏覽器上為 F12)，並將下列程式碼複製並貼到主控台中：

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

瀏覽器高度一律小於或等於螢幕高度，因為瀏覽器高度不包含瀏覽器導覽區或邊界。

## 將資料填入此維度中

此維度會從影像要求中的 [`bh` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 JavaScript 變數 `window.innerHeight` 在瀏覽器中收集這項資料。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在每次造訪的第一次點擊上包含 `bh` 查詢字串參數。

Adobe 會在造訪期間保存瀏覽器高度。如果瀏覽器高度在造訪期間有所調整，將不會記錄該調整。

## 維度項目

Dimension專案包含所有收集到的瀏覽器高度，並歸類到預先定義的群組中。 例如，如果點擊的瀏覽器高度為 `720`，則會將其歸類到維度項目 `700 to 799` 中。

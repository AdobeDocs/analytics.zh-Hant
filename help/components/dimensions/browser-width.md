---
title: 瀏覽器寬度 - 分段
description: 瀏覽器視窗的寬度 (像素)。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 88%

---


# 瀏覽器寬度

「瀏覽器寬度 - 分段」維度會顯示瀏覽器視窗的寬度，並將其歸類到以 100 像素為單位的群組中。如果您想要瞭解訪客以何種寬度範圍檢視您的內容，此維度就十分實用。瞭解您的內容在一般情況下受到檢視的寬度範圍，可讓您將內容最佳化以供檢視。

此維度與螢幕寬度不同。瀏覽器寬度是可檢視瀏覽器空間內的像素數，而螢幕寬度則是整個監視器的寬度 (像素)。如果您想在自己的電腦上觀察這兩個變數之間的差異，請開啟瀏覽器主控台 (在大部分的瀏覽器上為 F12)，並將下列程式碼複製並貼到主控台中：

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

瀏覽器寬度一律小於或等於螢幕寬度，因為瀏覽器寬度不包含捲軸或邊界。

## 將資料填入此維度中

此維度會從影像要求中的 [`bw` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 JavaScript 變數 `window.innerWidth` 在瀏覽器中收集這項資料。如果您使用 AppMeasurement 程式庫 (例如，透過 Adobe Experience Platform Launch)，此維度將可立即運作。如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在每次造訪的第一次點擊上包含 `bw` 查詢字串參數。

Adobe 會在造訪期間保存瀏覽器寬度。如果瀏覽器寬度在造訪期間有所調整，將不會記錄該調整。

## 維度項目

維度項目包括所有收集的瀏覽器寬度，分為100像素的群組。 For example, if the browser width of a hit is `1280`, then it is grouped in the dimension item `1200 to 1299`.

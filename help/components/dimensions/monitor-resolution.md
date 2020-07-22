---
title: 監視器解析度
description: 訪客螢幕的解析度（以像素為單位）。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---


# 監視器解析度

「螢幕解析度」尺寸會以像素顯示作用中顯示的高度和寬度。 當您想要瞭解「折疊」在您網站上對訪客的位置，或訪客瀏覽器視窗的寬度時，這個維度很實用。 瞭解折疊的位置可讓您最佳化內容以供檢視。

此尺寸與瀏覽器高度和寬度不同。 瀏覽器高度／寬度是可檢視瀏覽器空間內的像素數，而螢幕解析度是整個螢幕的像素數。 如果您想在自己的電腦上查看這兩個變數之間的差異，請開啟瀏覽器主控台（在大部分瀏覽器上為F12），並將下列程式碼複製並貼入主控台：

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

瀏覽器尺寸一律小於螢幕解析度，因為瀏覽器尺寸不包含瀏覽器導覽或邊界。

## 將資料填入此維度

此維度會從影像請求中的 [`s` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會使用JavaScript變數在瀏覽器中 `screen.width` 收集 `screen.height` 此資料。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在影像請求中包含 `s` 查詢字串參數。

## 維度項目

維度項目包含所有收集的螢幕解析度。 範例值 `1920 x 1080`包括、 `1366 x 768`和 `1280 x 720`。

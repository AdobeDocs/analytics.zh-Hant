---
title: 瀏覽器高度——範圍化
description: 瀏覽器視窗的高度（像素）。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# 瀏覽器高度

「瀏覽器高度——範圍化」維度會顯示瀏覽器視窗的高度，分為100像素的群組。 當您想要瞭解訪客在您網站上的「折疊」位置時，這個維度很實用。 瞭解折疊的位置可讓您最佳化內容以供檢視。

此尺寸與螢幕高度不同。 瀏覽器高度是可檢視瀏覽器空間內的像素數，而螢幕高度是整個螢幕的高度（以像素為單位）。 如果您想在自己的電腦上查看這兩個變數之間的差異，請開啟瀏覽器主控台（在大部分瀏覽器上為F12），並將下列程式碼複製並貼入主控台：

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

瀏覽器高度一律小於或等於螢幕高度，因為瀏覽器高度不包含瀏覽器導覽或邊界。

## 將資料填入此維度

此維度會從影像請求中的 [`bh` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會在瀏覽器中使用JavaScript變數 `window.innerHeight` 收集此資料。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在每次瀏覽的首次點擊中加入查詢字串參數。 `bh`

Adobe會在瀏覽時保留瀏覽器高度。 如果瀏覽器高度在瀏覽中期調整，則不會記錄調整。

## 維度項目

維度項目包括所有收集的瀏覽器高度，分為100像素的群組。 例如，如果點擊的瀏覽器高度為 `720`分組，則會在維度項目中分組 `700 to 799`。

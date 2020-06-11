---
title: 瀏覽器寬度——範圍化
description: 瀏覽器視窗的寬度（以像素為單位）。
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# 瀏覽器寬度

「瀏覽器寬度——範圍化」維度會顯示瀏覽器視窗的寬度，分為100像素的群組。 當您想要瞭解訪客對您內容的瞭解程度時，此維度很實用。 瞭解內容通常被檢視的範圍，可讓您最佳化內容以供檢視。

此尺寸與螢幕寬度不同。 瀏覽器寬度是可檢視瀏覽器空間內的像素數，而螢幕寬度是整個螢幕的寬度（以像素為單位）。 如果您想在自己的電腦上查看這兩個變數之間的差異，請開啟瀏覽器主控台（在大部分瀏覽器上為F12），並將下列程式碼複製並貼入主控台：

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

瀏覽器寬度一律小於或等於螢幕寬度，因為瀏覽器寬度不包含捲軸或邊框。

## 將資料填入此維度

此維度會從影像請求中的 [`bw` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會在瀏覽器中使用JavaScript變數 `window.innerWidth` 收集此資料。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），請務必在每次瀏覽的首次點擊中加入查詢字串參數。 `bw`

Adobe會保留瀏覽的瀏覽器寬度。 如果瀏覽器寬度在瀏覽中間時調整，則不會記錄調整。

## 維度值

維度值包含所有收集的瀏覽器寬度，分為100像素的群組。 例如，如果點擊的瀏覽器寬度為 `1280`，則會在維度值中分組 `1200 to 1299`。

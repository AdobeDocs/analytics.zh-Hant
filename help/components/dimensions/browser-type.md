---
title: 瀏覽器類型
description: 製作瀏覽器的組織。
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 3%

---


# 瀏覽器類型

「瀏覽器類型」維度會列出建立訪客使用之瀏覽器的組織。 當您想要查看訪客使用的主要瀏覽器時，此維度很實用。 它提供「瀏覽器」維度的值，因為它不會將相同瀏覽器的不同版本列為個別維度值。

## 將資料填入此維度

此維度會參照Adobe內部的查閱表格。 查閱值是以影像請求中 `User-Agent` 的HTTP標題為基礎。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。

## 維度值

維度值包括製作瀏覽器的組織。 常見維值 `"Google"` 包括 [!DNL Chrome](建立者 `"Apple"` )、(創 [!DNL Safari]建者)、 `"Microsoft"` (建立者 [!DNL Edge]) `"Mozilla"`[!DNL Firefox]和（建立者）。

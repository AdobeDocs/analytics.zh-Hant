---
title: 作業系統類型
description: 作業系統，不論版本為何。
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# 作業系統類型

「作業系統類型」維度會顯示訪客使用的整體作業系統，而不論特定版本為何。 此維度不僅有助於瞭解哪些特定作業系統和版本最常見，也有助於瞭解訪客使用哪些典型作業系統平台。

## 將資料填入此維度

此維度會參照Adobe內部的查閱表格。 查閱值是以影像請求中 `User-Agent` 的HTTP標題為基礎。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。

## 維度值

維值包括所用作業系統的類型。 Examples include `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, and `"Apple iOS"`.

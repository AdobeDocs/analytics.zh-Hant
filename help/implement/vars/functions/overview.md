---
title: 函數與方法
description: 瞭解如何在實施中使用 Adobe 提供的函數和方法。
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 100%

---

# 函數與方法

Adobe 提供數種您可在實施中使用的函數和方法。參考這些函數或方法時，它們會使用一行程式碼來執行常見工作。

其中部分一行程式碼屬於下列類別：

* **追蹤呼叫**：最常見的方法，在許多實施中非常重要。其中包括 [`t()`](t-method.md) 和 [`tl()`](tl-method.md) 方法。
* **AppMeasurement 公用程式**：在舊版 AppMeasurement 中，實施必須編寫自己的程式碼才能執行這些工作。Adobe 提供這些公用程式方法來簡化這些常見工作。AppMeasurement 公用程式包括 [`Util.cookieRead()`](util-cookieread.md)、[`Util.cookieWrite()`](util-cookiewrite.md) 和 [`Util.getQueryParam()`](util-getqueryparam.md)。
* **註冊功能**：您可以撰寫自己的函數，並讓 AppMeasurement 在將追蹤呼叫傳送至 Adobe 之前或之後，自動執行這些函數。屬於此類別的變數為 [`doPlugins()`](doplugins.md)、[`registerPreTrackCallback()`](registerpretrackcallback.md) 和 [`registerPostTrackCallback()`](registerposttrackcallback.md)。

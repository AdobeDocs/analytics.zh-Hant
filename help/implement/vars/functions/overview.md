---
title: 函式與方法
description: 瞭解如何使用Adobe在您的實作中提供的功能和方法。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 函式與方法

Adobe提供數種您可在實作中使用的函式和方法。 當您參考這些函式或方法時，這些函式或方法會使用一行程式碼來執行一般工作。

其中某些單行代碼屬於以下類別：

* **追蹤呼叫**:最常見的方法，在許多實作中都至關重要。 其中包括 [`t()`](t-method.md) 和方 [`tl()`](tl-method.md) 法。
* **AppMeasurement公用程式**:在舊版AppMeasurement中，實作必須編寫自己的程式碼才能執行這些工作。 Adobe提供這些公用程式方法來簡化這些常見工作。 AppMeasurement公用程 [`Util.cookieRead()`](util-cookieread.md)式包 [`Util.cookieWrite()`](util-cookiewrite.md)括、和 [`Util.getQueryParam()`](util-getqueryparam.md)。
* **註冊功能**:您可以編寫自己的函式，並讓AppMeasurement在傳送追蹤呼叫至Adobe之前或之後自動執行這些函式。 屬於此類別的變數 [`doPlugins()`](doplugins.md)有 [`registerPreTrackCallback()`](registerpretrackcallback.md)、和 [`registerPostTrackCallback()`](registerposttrackcallback.md)。

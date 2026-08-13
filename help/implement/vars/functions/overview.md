---
title: 函數與方法
description: 瞭解如何在實施中使用 Adobe 提供的函數和方法。
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 100%

---

# 函數與方法

Adobe 提供數種您可在實施中使用的函數和方法。 參考這些函數或方法時，它們會使用一行程式碼來執行常見工作。

其中部分一行程式碼屬於下列類別：

* **追蹤呼叫**：最常見的方法，在許多實施中非常重要。 其中包括 [`t()`](t-method.md) 和 [`tl()`](tl-method.md) 方法。
* **AppMeasurement 公用程式**：在舊版 AppMeasurement 中，實施必須編寫自己的程式碼才能執行這些工作。 Adobe 提供這些公用程式方法來簡化這些常見工作。 AppMeasurement 公用程式包括 [`Util.cookieRead()`](util-cookieread.md)、[`Util.cookieWrite()`](util-cookiewrite.md) 和 [`Util.getQueryParam()`](util-getqueryparam.md)。
* **註冊功能**：您可以撰寫自己的函數，並讓 AppMeasurement 在將追蹤呼叫傳送至 Adobe 之前或之後，自動執行這些函數。 屬於此類別的變數為 [`doPlugins()`](doplugins.md)、[`registerPreTrackCallback()`](registerpretrackcallback.md) 和 [`registerPostTrackCallback()`](registerposttrackcallback.md)。

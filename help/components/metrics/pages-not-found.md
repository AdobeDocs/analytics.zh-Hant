---
title: 找不到頁面
description: 包含錯誤的點擊數。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 5%

---


# 找不到頁面

*此說明頁面說明「找不到頁面」如何當成度量。 如需詳細[資訊，請參閱](../dimensions/pages-not-found.md)「找不到頁面」維度。*

「找不到頁面」度量會顯示頁面包含錯誤的點擊數。 當您想要查看哪些頁面或URL包含錯誤訊息（例如404）時，此量度很有用，因此您可以判斷錯誤的原因並加以修正。

## 此度量的計算方式

此度量會計算變數等 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 於值的所有點擊 `"errorPage"`。 它等同於「找不到頁 [面」維度](../dimensions/pages-not-found.md) 。
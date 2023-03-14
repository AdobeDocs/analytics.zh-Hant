---
title: 找不到頁面 (量度)
description: 包含錯誤的點擊次數。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 100%

---

# 找不到頁面

*此說明頁面說明「找不到頁面」作為量度時的運作方式。如需詳細資訊，請參閱[找不到頁面](../dimensions/pages-not-found.md)維度。*

「找不到頁面」量度會顯示頁面包含錯誤的點擊次數。如果您想要查看哪些頁面或 URL 包含錯誤訊息 (例如 404)，則可以利用此量度來判斷錯誤的原因，並加以修正。

## 此量度的計算方式

此量度會計入 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 變數等於 `"errorPage"` 值的所有點擊。此量度等同於[找不到頁面](../dimensions/pages-not-found.md)維度。

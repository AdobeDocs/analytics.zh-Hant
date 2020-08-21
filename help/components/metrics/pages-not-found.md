---
title: 找不到頁面
description: 包含錯誤的點擊次數。
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---


# 找不到頁面

*此說明頁面說明「找不到頁面」作為量度時的運作方式。如需詳細資訊，請參閱[找不到頁面](../dimensions/pages-not-found.md)維度。*

「找不到頁面」量度會顯示頁面包含錯誤的點擊次數。如果您想要查看哪些頁面或 URL 包含錯誤訊息 (例如 404)，則可以利用此量度來判斷錯誤的原因，並加以修正。

## 此量度的計算方式

此量度會計入 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 變數等於 `"errorPage"` 值的所有點擊。此量度等同於[找不到頁面](../dimensions/pages-not-found.md)維度。
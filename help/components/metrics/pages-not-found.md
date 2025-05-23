---
title: 找不到頁面 (量度)
description: 包含錯誤的點擊次數。
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 38%

---

# 找不到頁面

*此說明頁面說明「找不到頁面」作為量度時的運作方式。請參閱[找不到頁面](../dimensions/pages-not-found.md)維度頁面，以取得如何當做維度使用的詳細資訊。*

「找不到頁面」[量度](overview.md)顯示訪客發生錯誤時，維度已設定或持續存在的點選次數。 如果您想要檢視哪些頁面或URL包含錯誤訊息（例如404），此量度就十分實用。 然後，您可以將此資訊傳遞至您的Web開發團隊，由他們判斷錯誤的原因並加以修正。

## 此量度的計算方式

此量度會計入 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 變數等於 `"errorPage"` 值的所有點擊。此量度等同於[找不到頁面](../dimensions/pages-not-found.md)維度。

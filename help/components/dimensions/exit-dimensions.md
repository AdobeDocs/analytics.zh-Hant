---
title: 退出維度
description: 列出退出維度及其使用情形。
keywords: 退出頁面, 退出網站區域, 退出伺服器, 退出自訂分析
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 94%

---

# 退出維度

*此說明頁面說明退出作為[維度](overview.md)時的運作方式。 若要瞭解退出作為量度時的運作方式，請參閱[退出](../metrics/exits.md)量度。*

退出維度會記錄最後一個維度項目，並將其回溯套用至造訪中所有的點擊。報表套裝設定中的[流量變數](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)下方所有已啟用路徑分析的變數，都可使用退出維度。

## 將資料填入退出維度中

指定的退出維度以其相關聯的流量變數為基礎。如果非退出變數有資料，則其相關聯的退出維度也會包含資料。如果您的流量變數包含資料，即無須對退出維度進行實作變更。

## 維度項目

由於退出變數通常以您實作中的自訂字串為基礎，因此您的組織會決定維度項目。指定退出維度中的值會與其相關聯的非退出維度中的維度項目相符。例如，「退出頁面」維度中的維度項目，會與「頁面」維度中的維度項目相似。

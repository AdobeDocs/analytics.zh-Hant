---
title: 平日/週末
description: 判斷點擊是發生在工作日還是週末。
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 80%

---

# 平日/週末

「工作日/週末」[維度](overview.md)會針對點選是發生在工作日（星期一至星期五）還是週末（星期六至星期日）提供insight。 點擊的時間根據[報表套裝的時區](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)而定。

## 將資料填入此維度中

此維度可直接用於所有實施作業。如果報告套裝包含資料，此維度即會運作。

## 維度項目

此維度一律包含剛好兩個維度項目：`"Weekday"` 和 `"Weekend"`。維度項目 `"Weekday"` 會套用至星期一到星期五的所有點擊，而維度項目 `"Weekend"` 則套用至星期六和星期日的所有點擊。

---
title: 平日/週末
description: 判斷點擊是發生在工作日或週末。
translation-type: tm+mt
source-git-commit: 05ea2778cd5cd324c660fd0f1d2ac02373829f0f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# 平日/週末

「工作日／週末」維度可讓您分析點按是在工作日（星期一——星期五）或週末（星期六——星期日）發生。 The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## 將資料填入此維度

此維度適用於所有實作，不需開箱即用。 如果報表套裝包含資料，此維度會運作。

## 維度值

此維始終包含兩個維值： `"Weekday"` 和 `"Weekend"`。 維度值會套 `"Weekday"` 用至週一到週五的所有點擊，而維度值則 `"Weekend"` 會套用至週六和週日的所有點擊。

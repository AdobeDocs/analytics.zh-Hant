---
title: 平日/週末
description: 判斷點擊是發生在工作日或週末。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---


# 平日/週末

「工作日／週末」維度可讓您分析點按是在工作日（星期一——星期五）或週末（星期六——星期日）發生。 The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## 將資料填入此維度

此維度適用於所有實作，不需開箱即用。 如果報表套裝包含資料，此維度會運作。

## 維度項目

此維度一律包含兩個維度項目： `"Weekday"` 和 `"Weekend"`。 維度項目 `"Weekday"` 適用於週一到週五的所有點擊，而維度項目 `"Weekend"` 則適用於週六和週日的所有點擊。

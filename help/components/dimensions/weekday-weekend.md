---
title: 平日/週末
description: 判斷點擊是發生在工作日還是週末。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 68%

---


# 平日/週末

「工作日/週末」維度可讓您深入分析點擊是發生在工作日 (星期一 - 星期五) 還是週末 (星期六 - 星期日)。點擊的時間根據[報表套裝的時區](/help/admin/admin/general-acct-settings-admin.md)而定。

## 將資料填入此維度中

此維度可直接用於所有實作。如果報表套裝包含資料，此維度即會運作。

## 維度項目

This dimension always contains exactly two dimension items: `"Weekday"` and `"Weekend"`. The dimension item `"Weekday"` applies to all hits Monday through Friday, while the dimension item `"Weekend"` applies to all hits on Saturday and Sunday.

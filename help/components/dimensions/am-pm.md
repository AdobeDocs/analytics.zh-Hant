---
title: 上午/下午
description: 判斷點擊是否發生在上午或下午時間。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# 上午/下午

「AM/PM」維度可提供在AM或PM小時間是否發生點擊的分析。 The time of the hit is based on the [report suite&#39;s time zone](/help/admin/admin/general-acct-settings-admin.md).

## 將資料填入此維度

這個尺寸是現成可用的。 它沒有任何要更改的設定。 其唯一依賴性是報表套裝的時區，時區會決定哪些小時是AM，哪些是PM。

## 維度項目

此維度一律包含兩個維度項目： `"AM"` 和 `"PM"`。 維度項目 `"AM"` 會套用至從12:00 AM到11:59 AM的所有點擊，而維度項目則 `"PM"` 會套用至從12:00 PM到11:59 PM的所有點擊。

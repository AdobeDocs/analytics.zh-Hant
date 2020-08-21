---
title: 上午/下午
description: 判斷點擊發生在上午還是下午。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 70%

---


# 上午/下午

「上午/下午」維度可讓您深入瞭解點擊發生在上午還是下午。點擊的時間根據[報表套裝的時區](/help/admin/admin/general-acct-settings-admin.md)而定。

## 將資料填入此維度中

這是現成可用的維度。您無須變更其任何設定。其唯一的相依性在於報表套裝的時區，哪些時間屬於上、下午由此時區決定。

## 維度項目

This dimension always contains exactly two dimension items: `"AM"` and `"PM"`. The dimension item `"AM"` applies to all hits from 12:00 AM to 11:59 AM, while the dimension item `"PM"` applies to all hits from 12:00 PM to 11:59 PM.

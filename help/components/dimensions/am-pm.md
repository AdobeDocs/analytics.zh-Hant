---
title: 上午/下午
description: 判斷點擊發生在上午還是下午。
translation-type: ht
source-git-commit: cd2225ec00190af6b616f313b419935c4f8dfafd
workflow-type: ht
source-wordcount: '117'
ht-degree: 100%

---


# 上午/下午

「上午/下午」維度可讓您深入瞭解點擊發生在上午還是下午。點擊的時間根據[報表套裝的時區](/help/admin/admin/general-acct-settings-admin.md)而定。

## 將資料填入此維度中

這是現成可用的維度。您無須變更其任何設定。其唯一的相依性在於報表套裝的時區，哪些時間屬於上、下午由此時區決定。

## 維度項目

此維度一律包含剛好兩個維度項目：`"AM"` 和 `"PM"`。維度項目 `"AM"` 會套用至凌晨 12:00 到中午 11:59 的所有點擊，而維度項目 `"PM"` 則會套用至中午 12:00 到晚上 11:59 的所有點擊。

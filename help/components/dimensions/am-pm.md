---
title: 上午/下午
description: 判斷點擊發生在上午還是下午。
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 64%

---

# 上午/下午

&#39;AM/PM&#39; [維度](overview.md)會提供點選發生在上午還是下午insight。 點擊的時間根據[報表套裝的時區](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)而定。

## 將資料填入此維度中

這是現成可用的維度。您無須變更其任何設定。其唯一的相依性在於報表套裝的時區，哪些時間屬於上、下午由此時區決定。

## 維度項目

此維度一律包含剛好兩個維度項目：`"AM"` 和 `"PM"`。維度專案`"AM"`會套用至凌晨12:00到中午11:59的所有點選，而維度專案`"PM"`則會套用至中午12:00到晚上11:59的所有點選。

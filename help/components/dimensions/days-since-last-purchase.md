---
title: 上次購買間隔天數
description: 目前點擊與上次購買間隔的天數。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# 上次購買間隔天數

「上次購買間隔的天數」維度會測量訪客目前點擊與當時最近一次購買之間所經過的時間量。 此維度可協助您瞭解訪客在您網站上購買物品後的行為。

從未購買過物品的訪客不會納入此維度。 此外，訪客首次購買前引發的點擊也不包含在內。 僅包含訪客首次購買後的點擊。

## 將資料填入此維度

Adobe會根據您實作中的事件自 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 動填入此維度。 如果您在網站上實 `purchase` 作事件，此維度一律有效。

## 維度項目

維度項目包括訪客最近一次購買與目前點擊之間的天數。 每個天數是個別的維度項目，在同一天發生訪客最近一次購買和目前點擊的「同一天」。

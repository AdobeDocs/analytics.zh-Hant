---
title: 上次購買間隔天數
description: 目前點擊與上次進行購買的間隔天數。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---


# 上次購買間隔天數

「上次購買間隔天數」維度會測量訪客目前的點擊與當時最近一次購買之間所經過的時間長度。此維度可協助您了解訪客在您網站上購買商品後的行為。

從未購買過商品的訪客不會納入此維度中。此外，訪客首次購買前引發的點擊也不包含在內。僅包含訪客首次購買後的點擊。

## 將資料填入此維度中

Adobe 會根據您實作中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件自動填入此維度。如果您在網站上實作 `purchase` 事件，此維度一律有效。

## 維度項目

維度項目包含訪客最近一次購買與目前點擊的間隔天數。每個天數都是獨立的維度項目，若訪客的最近一次購買與目前點擊發生於同一天，則會出現「同一天」。

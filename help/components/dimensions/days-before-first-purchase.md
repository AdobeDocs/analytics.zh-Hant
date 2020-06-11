---
title: 首次購買前幾天
description: 訪客首次瀏覽與首次購買之間的天數。
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# 首次購買前幾天

「首次購買前的天數」維度會報告訪客首次瀏覽您網站和進行購買之間的間隔天數。 例如，如果訪客在第一次瀏覽後一天進行購買，則任何後續瀏覽或事件都屬於「1天」維度值。

訪客進行第一次購買後，在訪客的Cookie存留期剩餘時間內，他們屬於相同的維度值。

## 將資料填入此維度

Adobe會根據您實作中的事件自 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 動填入此維度。 如果您在網站上實 `purchase` 作事件，此維度一律有效。

## 維度值

維度值包括訪客首次瀏覽網站與首次購買之間的天數。 每個天數是個別的維度值，在訪客第一次瀏覽及第一次購買發生在同一天時，會發生「同一天」。

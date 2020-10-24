---
title: 首次購買間隔天數
description: 訪客首次造訪與首次購買之間的天數。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '173'
ht-degree: 100%

---


# 首次購買間隔天數

「首次購買間隔天數」維度報告訪客首次瀏覽網站和購買之間的間隔天數。舉例來說，如果訪客在首次造訪一天後購買，則所有後續造訪或事件都屬於「1 天」維度項目。

訪客首次購買後，就會在訪客的 Cookie 期限剩餘時間內屬於相同的維度項目。

## 將資料填入此維度中

Adobe 會根據您實作中的 [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) 事件自動填入此維度。如果您在網站上實作 `purchase` 事件，此維度一律有效。

## 維度項目

維度項目包括訪客首次造訪網站與首次購買之間的天數。每個天數都是個別的維度項目，若訪客的首次造訪與首次購買發生於同一天，則會出現「同一天」。

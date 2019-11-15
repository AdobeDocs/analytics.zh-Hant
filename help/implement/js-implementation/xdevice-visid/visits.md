---
description: Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: 瀏覽
topic: Developer and implementation
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 瀏覽

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。請參閱 [Adobe Experience cloud裝置合作檔案](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。

如果您查看[上表](/help/implement/js-implementation/xdevice-visid/visit-example.md)，則會發現這已發生 4 次: 在點擊 1、9、11 和 12。與訪客相仿，此值也會在初次產生關聯後恢復正常，因為[!UICONTROL 「瀏覽頁碼」]會因為有效[!UICONTROL 訪客 ID] 有所變更而重設為 1。

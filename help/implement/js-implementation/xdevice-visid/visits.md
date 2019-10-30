---
description: Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。
keywords: Analytics 實作
seo-description: Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。
seo-title: 瀏覽
solution: Analytics
subtopic: 訪客
title: 瀏覽
topic: 開發人員和實作
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 瀏覽

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。請參閱 [Adobe Experience cloud裝置合作檔案](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。

如果您查看[上表](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA)，則會發現這已發生 4 次: 在點擊 1、9、11 和 12。與訪客相仿，此值也會在初次產生關聯後恢復正常，因為[!UICONTROL 「瀏覽頁碼」]會因為有效[!UICONTROL 訪客 ID] 有所變更而重設為 1。

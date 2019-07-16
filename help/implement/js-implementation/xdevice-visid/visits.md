---
description: Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。
keywords: Analytics 實施
seo-description: Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。
seo-title: 瀏覽
solution: Analytics
subtopic: 訪客
title: 造訪
topic: 開發人員和實施
uuid: 3035be6f-6adc-45df-a3 f2-5de6 d3 ed99 ce
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 造訪次數

>[!IMPORTANT]
>
>不再建議這種識別跨裝置訪客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics 會在每次發生伺服器呼叫、且「瀏覽頁碼」等於 1 時計入一次瀏覽。

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 4 times: at hits 1, 9, 11, and 12. 與訪客相仿，此值也會在初次產生關聯後恢復正常，因為[!UICONTROL 「瀏覽頁碼」]會因為有效[!UICONTROL 訪客 ID] 有所變更而重設為 1。

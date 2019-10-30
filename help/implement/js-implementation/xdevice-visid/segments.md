---
description: 您可以在每次有指定的訪客 ID Cookie 產生關聯時建立區段。
keywords: Analytics 實作
seo-description: 您可以在每次有指定的訪客 ID Cookie 產生關聯時建立區段。
seo-title: 建立區段
solution: Analytics
title: 建立區段
topic: 開發人員和實作
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 建立區段

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。詳情請參閱[Adobe Experience Cloud Device Co-op 文件](https://marketing.adobe.com/resources/help/zh_TW/mcdc/)。

您可以在每次有指定的訪客 ID Cookie 產生關聯時建立區段。

根據[上表](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA)，若您建立了瀏覽數等於 9 的區段，其中將會包含伺服器呼叫 12 和 13。雖然伺服器呼叫 11 在技術上也屬於相同瀏覽的一部分，但該伺服器呼叫的歷史資料並未更改，瀏覽數也保持不變。

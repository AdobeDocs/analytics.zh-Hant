---
title: 找不到頁面
description: 在您的網站上傳回錯誤的URL。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# 找不到頁面

*此說明頁面說明「找不到頁面」如何當成維度。 如需詳細[資訊，請參閱](../metrics/pages-not-found.md)「找不到頁面」量度。*

「找不到頁面」維度會顯示包含錯誤的URL。 當您想要降低訪客在您網站上所收到的錯誤數時，此維度很實用。

* 您可以在「流量」視覺化中使 [用此維度](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) ，查看訪客點進哪些頁面以達到錯誤。 然後，您可以與組織中的開發團隊合作，以修正每個頁面上的連結。
* 您可以將此維度與「反向連 [結」維度搭配使用](referrer.md) ，以查看訪客從外部連結到達您網站的位置。 然後，您可以實作重新導向至所需位置，或與第三方合作以修正連結。

## 將資料填入此維度

此維度會從影像請求中的 [`pageType` 和 `g` 查詢字串](/help/implement/validate/query-parameters.md) 中擷取資料。 如果查 `pageType` 詢字串等 `errorPage`於，則 `g` 會記錄查詢字串（頁面URL）。 AppMeasurement會使用變數收集此 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 資料。 如果未 `pageType` 定義變數或設定變數為其他變數， `errorPage`則不會收集此維度的資料。

## 維度項目

維度項目包括發生錯誤之網站上頁面的URL。

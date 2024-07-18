---
title: 找不到頁面 (維度)
description: 在您的網站上傳回錯誤的 URL。
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 94%

---

# 找不到頁面

*此說明頁面說明「找不到頁面」作為[維度](overview.md)時的運作方式。 如需詳細資訊，請參閱[找不到頁面](../metrics/pages-not-found.md)量度。*

「找不到頁面」維度會顯示包含錯誤的 URL。如果您想要減少訪客在您網站上收到的錯誤，此維度就十分實用。

* 您可以在[流量視覺效果](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)中使用此維度，以查看訪客在點進哪些頁面之後遇到錯誤。然後，您可以與組織中的開發團隊合作，以修正每個頁面上的連結。
* 您可以將此維度與[反向連結](referrer.md)維度搭配使用，以查看訪客從何處透過外部連結到達您的網站。然後，您可以實作重新導向連至所需的位置，或與第三方合作以修正連結。

## 將資料填入此維度中

此維度會從影像要求中的 [`pageType` 和 `g` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。如果 `pageType` 查詢字串等同於 `errorPage`，則會記錄 `g` 查詢字串 (頁面 URL)。AppMeasurement 會使用 [`pageType`](/help/implement/vars/page-vars/pagetype.md) 變數收集這項資料。如果 `pageType` 變數未定義，或設為 `errorPage` 以外的其他項目，則不會收集此維度的資料。

## 維度項目

維度項目包含您的網站上發生錯誤之頁面的 URL。

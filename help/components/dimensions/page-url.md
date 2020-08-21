---
title: 頁面 URL
description: 頁面的 URL。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 92%

---


# 頁面 URL

「頁面 URL」維度會列出您網站上的 URL。

>[!IMPORTANT]
>
>此維度僅適用於 Data Warehouse。如果您想在其他 Analytics 解決方案中使用 URL 維度，請使用 [eVar](evar.md)。

## 將資料填入此維度中

此維度會從影像要求中的 [`g` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會使用 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 變數收集這項資料。

## 將 URL 填入 eVar 中

Adobe 建議將 eVar 設為串連字串 `window.location.hostname + window.location.pathname`。此字串的效用通常會優於 `window.location.href`，因為它省略了通訊協定、查詢字串和錨點標記。

如果您想要讓 eVar 完全符合 Data Warehouse 中的「頁面 URL」維度，您可以使用[動態變數](/help/implement/vars/page-vars/dynamic-variables.md)，並將 eVar 設為每個點擊上的 `D=g`。請注意，此方法不適用於自訂連結點擊，因為所有 [`tl()`](/help/implement/vars/functions/tl-method.md) 呼叫的頁面 URL 都會被移除。

## 維度項目

維度項目包含您網站上頁面的URL。

---
title: 頁面 URL
description: 頁面的 URL。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 64%

---


# 頁面 URL

「頁面 URL」維度會列出您網站上的 URL。

>[!IMPORTANT]
>
>此維度僅適用於 Data Warehouse。如果您想要在其他Analytics解決方案中使用URL維度，請考慮在每次點擊時將值復 [制到eVar](evar.md) 。

## 將資料填入此維度中

This dimension retrieves data from the [`g` and `-g` query strings](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [連結追蹤呼叫(`tl()`)](/help/implement/vars/functions/tl-method.md) ，即使查詢字串存在，也一律 `g` 會移除此維度。

有時 URL 的長度會超過 255 個位元組。AppMeasurement 會針對影像要求中 URL 的前 255 個位元組使用 `g` 查詢字串參數。如果 URL 的長度超過 255 個位元組，其餘的 URL 會儲存在 `-g` 查詢字串參數中。此變數包含 URL 中的通訊協定和查詢字串。

AppMeasurement會根據頁面的URL自動收集此資料。 您可以使用變數覆寫收集的 [`pageURL`](/help/implement/vars/page-vars/pageurl.md) 值。

## 將 URL 填入 eVar 中

Adobe 建議將 eVar 設為串連字串 `window.location.hostname + window.location.pathname`。此字串的效用通常會優於 `window.location.href`，因為它省略了通訊協定、查詢字串和錨點標記。

如果您想要讓 eVar 完全符合 Data Warehouse 中的「頁面 URL」維度，您可以使用[動態變數](/help/implement/vars/page-vars/dynamic-variables.md)，並將 eVar 設為每個點擊上的 `D=g`。

## 維度項目

維度項目包含您網站上頁面的URL。

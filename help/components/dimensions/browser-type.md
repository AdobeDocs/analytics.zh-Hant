---
title: 瀏覽器類型
description: 製作瀏覽器的組織。
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '133'
ht-degree: 100%

---


# 瀏覽器類型

「瀏覽器類型」維度會列出製作訪客所使用瀏覽器的組織。若想查看訪客使用的主要瀏覽器，此維度相當實用。它提供「瀏覽器」維度的值，不會將相同瀏覽器的不同版本列為單獨的維度項目。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 程式庫 (例如，透過 Adobe Experience Platform Launch)，此維度將可立即運作。

## 維度項目

維度項目包括製作瀏覽器的組織。常見維度項目包含 `"Google"` ([!DNL Chrome] 的製作者)、`"Apple"` ([!DNL Safari] 的製作者)、`"Microsoft"` ([!DNL Edge] 的製作者) 和 `"Mozilla"` ([!DNL Firefox] 的製作者)。

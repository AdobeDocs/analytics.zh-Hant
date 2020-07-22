---
title: Java 已啟用
description: 確定瀏覽器中是否啟用了Java。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 1%

---


# Java 已啟用

「啟用Java」維度會決定瀏覽器當時是否啟用Java。 若您想在網站上引入Java功能，並想瞭解已啟用Java的訪客數量，則此功能十分有用。 對於已禁用Java的用戶，可以提供其他選項或如何啟用它的說明。

## 將資料填入此維度

此維度會從影像請求中的 [`v` 查詢字串](/help/implement/validate/query-parameters.md) ，擷取資料。 AppMeasurement會偵測瀏覽器中是否啟用Java，以收集此資料。 如果您使用AppMeasurement程式庫（例如透過Adobe Experience Platform Launch），此維度就可立即運作。 如果您在AppMeasurement以外使用資料收集方法（例如透過API），如果您想要使用此維度，請務必包含包含 `v` &quot;Y&quot;或&quot;N&quot;的查詢字串參數。

## 維度項目

維度項目包括「已啟用」、「已停用」和「未知」。

* **啟用**: 在瀏覽器中啟用Java。 查 `v` 詢字串包含值&quot;Y&quot;。
* **停用**: Java在瀏覽器中已停用，或不支援Java。 查 `v` 詢字串包含值&quot;N&quot;。
* **未知**: AppMeasurement無法判斷Java支援。 查 `v` 詢字串不存在於影像要求中。

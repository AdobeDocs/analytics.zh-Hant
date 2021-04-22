---
title: Java 已啟用
description: 判斷瀏覽器中是否啟用 Java。
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '216'
ht-degree: 100%

---

# Java 已啟用

「Java 已啟用」維度會判斷瀏覽器當時是否已啟用 Java。若您想在網站上引入 Java 功能，並想了解已啟用 Java 的訪客數量，則此功能就很實用。對於已停用 Java 的使用者，您可以提供其他選項或啟用說明。

## 將資料填入此維度中

此維度會從影像要求中的 [`v` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。AppMeasurement 會偵測瀏覽器中是否啟用 Java，以收集此資料。如果您使用 AppMeasurement 程式庫 (例如，透過 Adobe Experience Platform Launch)，此維度將可立即運作。如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，且想要使用此維度，請務必加入包含「Y」或「N」的 `v` 查詢字串參數。

## 維度項目

維度項目包含「已啟用」、「已停用」和「未知」。

* **已啟用**：瀏覽器中已啟用 Java。`v` 查詢字串包含「Y」值。
* **已停用**：瀏覽器中已停用 Java，或不支援 Java。`v` 查詢字串包含「N」值。
* **未知**：AppMeasurement 無法判斷 Java支援。`v` 查詢字串不存在於影像要求中。

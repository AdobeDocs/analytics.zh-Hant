---
title: Java 已啟用
description: 判斷瀏覽器中是否啟用 Java。
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 93%

---

# Java 已啟用

&#39;Java已啟用&#39; [維度](overview.md)會判斷瀏覽器當時是否已啟用Java。 若您想在網站上引入 Java 功能，並想了解已啟用 Java 的訪客數量，則此功能就很實用。 對於已停用 Java 的使用者，您可以提供其他選項或啟用說明。

## 將資料填入此維度中

此維度會從影像要求中的 [`v` 查詢字串](/help/implement/validate/query-parameters.md)擷取資料。 AppMeasurement 會偵測瀏覽器中是否啟用 Java，以收集此資料。 如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，且想要使用此維度，請務必加入包含「Y」或「N」的 `v` 查詢字串參數。

## 維度項目

維度項目包含「已啟用」、「已停用」和「未知」。

* **已啟用**：瀏覽器中已啟用 Java。 `v` 查詢字串包含「Y」值。
* **已停用**：瀏覽器中已停用 Java，或不支援 Java。 `v` 查詢字串包含「N」值。
* **未知**：AppMeasurement 無法判斷 Java支援。 `v` 查詢字串不存在於影像要求中。

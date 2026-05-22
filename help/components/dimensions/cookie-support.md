---
title: Cookie 支援
description: 判斷瀏覽器是否支援 Cookie。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
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
source-wordcount: 188
ht-degree: 92%

---

# Cookie 支援

「Cookie支援」 [維度](overview.md)會報告瀏覽器是否支援指定點選的Cookie。 這可用來判斷使用支援 Cookie 的瀏覽器之訪客與有意停用 Cookie 的訪客比例。

## 將資料填入此維度中

此維度會從影像要求中的 [`k` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。 AppMeasurement 會嘗試設定名為 `s_cc` 的 Cookie，然後偵測該 Cookie 是否存在。 結果查詢字串參數值會是 `Y` (如果瀏覽器支援且已啟用 Cookie) 或 `N` (如果瀏覽器已停用 Cookie)。 如果您使用 AppMeasurement (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在具有 `Y` 或 `N` 值的每個點擊上包含 `k` 查詢字串參數。

## 維度項目

維度項目包括 `Enabled`、`Disabled` 和 `Unknown`。

* **`Enabled`**：瀏覽器支援 Cookie 且已啟用。
* **`Disabled`**：瀏覽器不支援 Cookie，或訪客已停用。
* **`Unknown`**：AppMeasurement 無法判斷 Cookie 支援。 `k` 查詢字串不存在於影像要求中。

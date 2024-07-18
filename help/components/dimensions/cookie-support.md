---
title: Cookie 支援
description: 判斷瀏覽器是否支援 Cookie。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 92%

---

# Cookie 支援

「Cookie支援」 [維度](overview.md)會報告瀏覽器是否支援指定點選的Cookie。 這可用來判斷使用支援 Cookie 的瀏覽器之訪客與有意停用 Cookie 的訪客比例。

## 將資料填入此維度中

此維度會從影像要求中的 [`k` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。AppMeasurement 會嘗試設定名為 `s_cc` 的 Cookie，然後偵測該 Cookie 是否存在。結果查詢字串參數值會是 `Y` (如果瀏覽器支援且已啟用 Cookie) 或 `N` (如果瀏覽器已停用 Cookie)。如果您使用 AppMeasurement (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。 如果您使用 AppMeasurement 以外的資料收集方法 (例如透過 API)，請務必在具有 `Y` 或 `N` 值的每個點擊上包含 `k` 查詢字串參數。

## 維度項目

維度項目包括 `Enabled`、`Disabled` 和 `Unknown`。

* **`Enabled`**：瀏覽器支援 Cookie 且已啟用。
* **`Disabled`**：瀏覽器不支援 Cookie，或訪客已停用。
* **`Unknown`**：AppMeasurement 無法判斷 Cookie 支援。`k` 查詢字串不存在於影像要求中。

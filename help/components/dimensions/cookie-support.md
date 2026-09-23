---
title: Cookie 支援
description: 判斷瀏覽器是否支援 Cookie。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 38%
---
# Cookie 支援

「Cookie支援」 [維度](overview.md)會報告瀏覽器是否支援指定點選的Cookie。 這可用來判斷使用支援 Cookie 的瀏覽器之訪客與有意停用 Cookie 的訪客比例。

## 將資料填入此維度中

Cookie支援是自動收集的，使用者端： AppMeasurement會嘗試設定名為`s_cc`的Cookie，然後報告其是否存在 — `Y` （如果瀏覽器支援且已啟用Cookie）或`N` （如果停用Cookie）。 可直接用於任何AppMeasurement或Web SDK （標籤）實作，且沒有變數可供設定。 如果您在AppMeasurement或Web SDK之外（例如透過API）收集資料，請在每次點選時傳送`Y`或`N`。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（自動收集） |
| **網頁SDK / XDM欄位** | 無（自動收集） |
| **查詢引數** | [`k`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<cookiesEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 1位元組 |
| **持續性** | 不適用 |

## 維度項目

維度項目包括 `Enabled`、`Disabled` 和 `Unknown`。

* **`Enabled`**：瀏覽器支援 Cookie 且已啟用。
* **`Disabled`**：瀏覽器不支援 Cookie，或訪客已停用。
* **`Unknown`**：AppMeasurement 無法判斷 Cookie 支援。 `k` 查詢字串不存在於影像要求中。

---
title: Java 已啟用
description: 判斷瀏覽器中是否啟用 Java。
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
source-wordcount: '249'
ht-degree: 51%
---
# Java 已啟用

&#39;Java已啟用&#39; [維度](overview.md)會判斷瀏覽器當時是否已啟用Java。 若您想在網站上引入 Java 功能，並想了解已啟用 Java 的訪客數量，則此功能就很實用。 對於已停用 Java 的使用者，您可以提供其他選項或啟用說明。

## 將資料填入此維度中

會自動收集已啟用的Java，使用者端： AppMeasurement會偵測瀏覽器中是否已啟用Java，並回報「Y」或「N」。 可直接用於任何AppMeasurement或Web SDK （標籤）實作，且沒有變數可供設定。 如果您在AppMeasurement或網頁SDK之外（例如透過API）收集資料，請傳送「Y」或「N」以使用此維度。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（自動收集） |
| **網頁SDK / XDM欄位** | 無（自動收集） |
| **查詢引數** | [`v`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML標籤** | [`<javaEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **位元組限制** | 1位元組 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含「已啟用」、「已停用」和「未知」。

* **已啟用**：瀏覽器中已啟用 Java。 `v` 查詢字串包含「Y」值。
* **已停用**：瀏覽器中已停用 Java，或不支援 Java。 `v` 查詢字串包含「N」值。
* **未知**：AppMeasurement 無法判斷 Java支援。 `v` 查詢字串不存在於影像要求中。

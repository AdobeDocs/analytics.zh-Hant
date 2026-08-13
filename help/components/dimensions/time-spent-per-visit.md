---
title: 每次造訪逗留時間 (維度)
description: 造訪花費的總時間。
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
TQID: 'https://experienceleague.adobe.com/jtBAAq-Pe0PyCQJPwvzwnK9eLv14CxTvrVQP4lvWy7k'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 92%

---

# 每次造訪逗留時間

*此說明頁面說明「每次造訪逗留時間」作為個別[維度](overview.md)的運作方式。 如需詳細資訊，請參閱[每次造訪逗留時間](../metrics/time-spent-per-visit.md)量度。*

「每次造訪逗留時間」維度會記錄訪客整次造訪逗留的時間量。 此維度使用下列步驟來測量計算：

1. 查看造訪之第一次點擊的時間戳記。
2. 將此點擊與造訪的上次點擊時間戳記進行比較。
3. 這兩次點擊之間經過的時間會計為逗留時間。

當您想要了解訪客一般與您網站的互動時間長度時，這些維度就很實用。

>[!TIP]
>
>逗留時間需要一次造訪中至少有兩次點擊，以測量時間。 單一點擊的造訪不會顯示在此維度中。

此維度是以造訪為基礎，表示值會套用於造訪內的每次點擊且不會變更。 將此維度與[頁面逗留時間](time-spent-on-page.md) (以點擊為基礎的維度) 作比較。

此維度與[「網站平均逗留時間」](../metrics/average-time-on-site.md)和[「每次造訪逗留時間」](../metrics/time-spent-per-visit.md)量度有關。

## 將資料填入此維度中

這些維度可直接用於所有實施作業。 如果報表套裝包含資料，這些維度即會運作。

## 維度項目

每次造訪逗留時間有多個維度：

* **每次造訪逗留時間 - 分段**：時間量會分段。 維度項目的範圍介於 `"Less than 1 minute"` 到 `"More than 15 hours"` 之間。 造訪通常不超過 12 個小時；不過，如果使用時間戳記點擊或資料來源，造訪可能會超過 12 個小時。
* **每次造訪逗留時間 - 精細**：每個秒數都是一個不重複的維度項目。 此維度無法在Data Warehouse中使用。

如需更多關於逗留時間的一般資訊，請參閱[逗留時間概觀](../metrics/time-spent.md)。

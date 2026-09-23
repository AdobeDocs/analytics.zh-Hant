---
title: 大量資料插入 API
description: 大量資料插入API (BDIA)是Adobe Analytics的功能，可讓您以批次檔案的方式上傳伺服器呼叫資料，而不需使用AppMeasurement等使用者端資料庫。
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: 'https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
    internal-label: Data sources
role_v2:
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
source-wordcount: '228'
ht-degree: 53%
---
# 大量資料插入 API

大量資料插入解決了好幾個使用案例，例如：

* 從之前的 Analytics 系統中擷取歷史資料

* 內部 Analytics 收集系統使得使用 AppMeasurement 變成不可行。 您可以使用 Extract-Transform-Load (ETL) 流程將資料放入批次檔案，然後使用 BDIA 將它們上傳到 Adobe Analytics。

* 從僅有間歇性連線至網際網路的裝置進行資料收集。 這些裝置會儲存互動，直到接收到連線。 然後裝置可以透過 BDIA 將所有資料一次上傳。

資料插入API和[大量資料插入API](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/)都是將伺服器端集合資料提交至Adobe Analytics的方法。 「資料插入 API」呼叫一次只處理一個事件。 「大量資料插入 API」接受含有事件資料的 CSV 格式檔案 (其中每一行儲存一個事件)。 如果您正在實施新的伺服器端收集，Adobe建議使用大量資料插入API。

如需驗證、端點、檔案格式、欄參考和疑難排解，請參閱Adobe Developer上的[大量資料插入API](https://developer.adobe.com/analytics-collection-apis/methods/bulk-data-insertion/)檔案。

---
title: 大量資料插入 API
description: 大量資料插入API (BDIA)是Adobe Analytics的功能，可讓您以批次檔案的方式上傳伺服器呼叫資料，而不需使用AppMeasurement等使用者端資料庫。
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 84%

---

# 大量資料插入 API

大量資料插入解決了好幾個使用案例，例如：

* 從之前的 Analytics 系統中擷取歷史資料

* 內部 Analytics 收集系統使得使用 AppMeasurement 變成不可行。您可以使用 Extract-Transform-Load (ETL) 流程將資料放入批次檔案，然後使用 BDIA 將它們上傳到 Adob&#x200B;&#x200B;e Analytics。

* 從僅有間歇性連線至網際網路的裝置進行資料收集。這些裝置會儲存互動，直到接收到連線。然後裝置可以透過 BDIA 將所有資料一次上傳。

資料插入 API 和[大量資料插入 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 兩者都是將伺服器端收集到的資料提交至 Adobe Analytics 的方法。每發生一個事件時，「資料插入 API」都會被呼叫。「大量資料插入 API」接受含有事件資料的 CSV 格式檔案 (其中每一行儲存一個事件)。若您正在實作新的伺服器端蒐集作業，建議採用「大量資料插入 API」。

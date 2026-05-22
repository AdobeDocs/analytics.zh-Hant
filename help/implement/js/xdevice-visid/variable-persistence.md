---
description: 若訪客輪廓在與相同的訪客 ID 變數產生關聯後合併，歷史資料集中的歸因分配並不會變更。
keywords: Analytics 實施作業
title: 歸因分配和持續性
feature: Implementation Basics
exl-id: 7a6305f6-c8ec-4f26-8373-45ce586bc69d
role: Developer
TQID: https://experienceleague.adobe.com/rEt9Nkt-c4sU08h-iYozgQmc1-N7RKWGNHzc-MOWja4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 558
ht-degree: 66%

---

# 歸因分配和持續性

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。 請參閱元件使用指南中的[跨裝置分析](/help/components/cda/overview.md)。

若訪客輪廓在與相同的訪客 ID 變數產生關聯後合併，歷史資料集中的歸因分配並不會變更。

* 設定`visitorID`變數並在點選時傳送時，Adobe會檢查是否有任何其他訪客資料具有相符的訪客ID。
* 如果設定檔存在，則會從該時間點開始使用系統中已存在的訪客設定檔，且不再使用先前的訪客設定檔。
* 若找不到相符的訪客ID，則會建立新的訪客資料。

當未驗證的客戶首次進入您的網站時，Adobe Analytics會為該客戶指派一個訪客設定檔。 當建立新的訪客輪廓時，某個瀏覽會結束，而另一個瀏覽則會開始。

## 範例 1

底下範例說明當使用者第一次在第一個裝置上進行驗證時，如何將資料傳送至 Adobe Analytics：

* `eVar16` 1 天後過期，而 `evar17` 只要瀏覽即過期。
* `post_visitor_id` 欄代表 Adobe Analytics 所維護的訪客輪廓。 貼文欄通常會顯示在資料摘要中。 請參閱匯出使用手冊中的[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)。
* `post_evar16` 和 `post_evar17` 欄顯示 eVar 的持續性。
* `cust_visid` 代表 `visitorID` 中設定的值。
* 每一列為一個「點擊」，此為傳送至 Adobe Analytics 資料收集伺服器的單一要求。

![跨裝置範例 1](assets/xdevice_first.jpg)

在包含先前所無法識別之 `visitorID` 值 (`u999` 以上) 的第一個資料連線上，建立一個新的輪廓。 先前設定檔中的持續值會傳輸到新設定檔。

* 設為瀏覽時即過期的 eVar 不會複製至已驗證的輪廓。 請注意，值 `car` 以上不會持續存在。
* 設為透過其他措施來過期的 eVar 將複製至已驗證的輪廓。 請注意，值 `apple` 持續存在。
* 對於持續存在的 eVar，不會記錄任何「例項」度量。 換句話說，使用跨裝置訪客身分識別時，eVar值的「不重複造訪」量度可能會大於「例項」量度的報表。

>[!NOTE]
>
>如果使用者第一次造訪您的網站 (以前從未在此裝置上造訪過)，而且在到達後大約三分鐘內進行驗證，則沒有任何值將持續保存至已驗證的訪客輪廓。

## 範例 2

底下範例說明先前在不同裝置上進行驗證之後，當客戶在新裝置上進行驗證時，如何將資料傳送至 Adobe Analytics。

![跨裝置範例 2](assets/xdevice-subsequent.jpg)

客戶進行驗證時，會與先前的「已驗證」輪廓 `2947539300` 進行比對。 本次訪問開始時使用的輪廓 (`5477766334477`) 將不再使用，檔案中不會保留任何資料。

* 地域劃分資料會根據第一次的造訪點選進行記錄，不會因為單一造訪而變更，無論使用何種裝置皆然。 這表示在新裝置上的後續資料連線中，通常不包含地域劃分資料。
* 瀏覽器、作業系統和色彩深度等技術欄會記錄在造訪的第一次點選上。 如同地域劃分值一樣，它們將不會複製至裝訂的輪廓。
* 行銷管道會覆寫後續資料連線 (其中包含該裝置的第一個驗證) 上的其他管道。

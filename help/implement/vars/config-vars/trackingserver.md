---
title: trackingServer
description: 用來透過HTTP將資料傳送至Adobe的網域。
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/6H8uZ4J-mT8NcC4OiiTgtBnP8eAgaMMzxzUHkS-9kGs'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 19%

---

# trackingServer

>[!IMPORTANT]
>
>此變數已遭取代。 有了HTTPS盛行，請改用[`trackingServerSecure`](trackingserversecure.md)。

`trackingServer`變數決定了AppMeasurement用來透過HTTP將資料傳送至Adobe的網域。 如果此變數未正確定義，您的實作可能會遭遇資料遺失。

在[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home)之前，此變數也會決定協力廠商Cookie的設定位置。 Adobe強烈建議儘可能在所有實施中使用ID服務。

如果未設定[`trackingServerSecure`](trackingserversecure.md)，AppMeasurement會使用`trackingServer`作為遞補。 許多較舊實作未設定`trackingServerSecure`，使用`trackingServer`作為安全頁面的遞補內容。 由於HTTPS非常普遍，Adobe建議儘可能使用`trackingServerSecure`。

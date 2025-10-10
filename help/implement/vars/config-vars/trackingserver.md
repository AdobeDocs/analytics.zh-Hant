---
title: trackingServer
description: 用來透過HTTP將資料傳送至Adobe的網域。
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 13%

---

# trackingServer

>[!IMPORTANT]
>
>此變數已遭取代。 有了HTTPS盛行，請改用[`trackingServerSecure`](trackingserversecure.md)。

`trackingServer`變數決定了AppMeasurement用來透過HTTP將資料傳送至Adobe的網域。 如果此變數未正確定義，您的實作可能會遭遇資料遺失。

在[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/zh-hant/docs/id-service/using/home)之前，此變數也會決定協力廠商Cookie的設定位置。 Adobe強烈建議儘可能在所有實施中使用ID服務。

如果未設定`trackingServer`，AppMeasurement會使用[`trackingServerSecure`](trackingserversecure.md)作為遞補。 許多較舊實作未設定`trackingServerSecure`，使用`trackingServer`作為安全頁面的遞補內容。 由於HTTPS非常普遍，Adobe建議儘可能使用`trackingServerSecure`。

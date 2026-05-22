---
title: account
description: （已淘汰）決定要將資料傳送到的報表套裝。
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/ICQkj-Eo29jve35GewuZUKOPIr01g-WjhbyztrAO0jI'
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>此變數已淘汰。 如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。 必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* 如果您使用Web SDK，報表套裝會位在Web SDK傳送資料的目標資料流的Adobe Analytics服務設定中。
* 如果您使用Adobe Analytics擴充功能，設定Adobe Analytics擴充功能時，報表套裝位於[!UICONTROL 資料庫管理]摺疊式功能表底下。
* 如果您使用[`s_gi()`](../functions/s-gi.md)函式將Analytics追蹤物件例項化，則報表套裝ID已作為函式中的必要引數存在。

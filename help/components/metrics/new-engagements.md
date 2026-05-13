---
title: 新參與
description: 首次接觸管道的設定次數。
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 83%

---

# 新參與

「新參與」量度[度量](overview.md)會顯示訪客在其參與期間內首次符合行銷管道的次數。 如果您想要比較任何有訪客首次符合行銷管道處理規則的維度，此量度就十分實用。

## 此量度的計算方式

在資料處理期間，每次點擊都會透過[行銷管道處理規則](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)執行。 如果點擊符合任何行銷管道處理規則，且訪客還沒有首次接觸管道，該點擊就是新的參與。 如果點擊不符合任何行銷管道處理規則，或如果訪客已有首次接觸管道，該點擊就不是新的參與。

訪客的訪客參與期間若過期，將可以有多個新的參與。

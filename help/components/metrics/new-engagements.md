---
title: 新增參與
description: 首次接觸管道的設定次數。
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 83%

---

# 新增參與

「新參與」量度[度量](overview.md)會顯示訪客在其參與期間內首次符合行銷管道的次數。 如果您想要比較任何有訪客首次符合行銷管道處理規則的維度，此量度就十分實用。

## 此量度的計算方式

在資料處理期間，每次點擊都會透過[行銷管道處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)執行。如果點擊符合任何行銷管道處理規則，且訪客還沒有首次接觸管道，該點擊就是新的參與。如果點擊不符合任何行銷管道處理規則，或如果訪客已有首次接觸管道，該點擊就不是新的參與。

訪客的訪客參與期間若過期，將可以有多個新的參與。

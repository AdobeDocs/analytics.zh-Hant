---
title: 具有 Experience Cloud ID 的使用者
description: 跨裝置分析中擁有ECID的人數。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 0ba418a49e6a226540e0791f0138027566022d6f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 28%
---
# 具有 Experience Cloud ID 的使用者

「具有Experience Cloud ID的使用者」是[跨裝置分析](../cda/overview.md)量度，其中顯示Adobe使用[訪客ID服務](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home)或[網頁SDK](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/identity/overview)識別的[使用者](people.md)的數量。

## 此量度的計算方式

在考慮每個[人員](people.md) （已識別或未識別）的情況下，如果點選包含`mid`查詢字串（根據[`s_ecid`](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/cookies/analytics) Cookie），則此[量度](overview.md)會增加。

您可以使用 ID 服務建立計算量度 `[People with ECID] ÷ [People]`，以獲取您網站的訪客百分比。

如需有關ECID的重要性以及對設定進行偵錯的詳細資訊，請參閱等同於非CDA量度的[具有Experience Cloud ID](visitors-with-ecid.md)的訪客。

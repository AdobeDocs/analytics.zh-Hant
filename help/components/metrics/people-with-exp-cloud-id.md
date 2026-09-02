---
title: 具有 Experience Cloud ID 的使用者
description: 跨裝置分析中具有 Experience Cloud ID 的使用者數量。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 58%

---

# 具有 Experience Cloud ID 的使用者

「具有Experience Cloud ID的使用者」是[跨裝置分析](../cda/overview.md)量度，其中顯示Adobe使用[訪客ID服務](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home)或[Experience Platform Identity服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/home)識別的[使用者](people.md)的數量。

## 此量度的計算方式

在考慮每個[人員](people.md) （已識別或未識別）的情況下，如果點選包含`mid`查詢字串（根據[`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookie），則此[量度](overview.md)會增加。

您可以使用 ID 服務建立計算量度 `[People with ECID] ÷ [People]`，以獲取您網站的訪客百分比。

如需有關 Experience Cloud ID 的重要性以及對設定進行偵錯的更多資訊，請查看等同於非 CDA 量度的「[具有 Experience Cloud ID 的訪客](visitors-with-ecid.md)」。

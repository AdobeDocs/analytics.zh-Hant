---
title: 具有 Experience Cloud ID 的使用者
description: 跨裝置分析中具有 Experience Cloud ID 的使用者數量。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 83%

---

# 具有 Experience Cloud ID 的使用者

「具有 Experience Cloud ID 的訪客」指會顯示 Adobe 使用 [Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant) 服務識別的[使用者](people.md)數量的「[跨裝置分析](../cda/overview.md)」量度。

## 此量度的計算方式

在考慮每個[人員](people.md) （已識別或未識別）的情況下，如果點選包含[查詢字串（根據](overview.md)`mid` Cookie），則此[`s_ecid`量度](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)會增加。

您可以使用 ID 服務建立計算量度 `[People with ECID] ÷ [People]`，以獲取您網站的訪客百分比。

如需有關 Experience Cloud ID 的重要性以及對設定進行偵錯的更多資訊，請查看等同於非 CDA 量度的「[具有 Experience Cloud ID 的訪客](visitors-with-ecid.md)」。

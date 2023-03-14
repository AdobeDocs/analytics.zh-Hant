---
title: 具有 Experience Cloud ID 的使用者
description: 跨裝置分析中具有 Experience Cloud ID 的使用者數量。
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 100%

---

# 具有 Experience Cloud ID 的使用者

「具有 Experience Cloud ID 的訪客」指會顯示 Adobe 使用 [Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant) 服務識別的[使用者](people.md)數量的「[跨裝置分析](../cda/overview.md)」量度。

## 此量度的計算方式

在考慮每個[使用者](people.md) (含已識別或未識別) 的情況下，如果點擊包含`mid`查詢字串 (根據 [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) Cookie)，則此量度會增加。

您可以使用 ID 服務建立計算量度 `[People with ECID] ÷ [People]`，以獲取您網站的訪客百分比。

如需有關 Experience Cloud ID 的重要性以及對設定進行偵錯的更多資訊，請查看等同於非 CDA 量度的「[具有 Experience Cloud ID 的訪客](visitors-with-ecid.md)」。

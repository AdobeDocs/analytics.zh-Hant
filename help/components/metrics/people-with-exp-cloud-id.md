---
title: 擁有 Experience Cloud ID 的使用者
description: 跨裝置分析中擁有Experience CloudID的人數。
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 21%

---

# 擁有 Experience Cloud ID 的使用者

「具有Experience CloudID的人」是[跨裝置分析](../cda/overview.md)量度，可顯示使用[Experience CloudID服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)Adobe識別的[人員](people.md)數量。

## 此量度的計算方式

考量到每個[People](people.md)（已識別或未識別），如果點擊包含`mid`查詢字串（根據[`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=zh-Hant) Cookie），此量度會增加。

您可以建立計算量度`[People with ECID] ÷ [People]`，以使用ID服務取得您網站的訪客百分比。

如需有關Experience CloudID重要性及除錯設定的詳細資訊，請參閱等同的非CDA量度[具有Experience CloudID](visitors-with-ecid.md)的訪客。

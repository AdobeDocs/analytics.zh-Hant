---
title: 訂購
description: 進行購買的次數。
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 84%

---

# 訂購

「訂單」 [量度](overview.md) 顯示您的網站上發生的購買事件總數。 此量度對於電子商務網站的測量轉換至關重要。您可以將此量度與任何維度結合，了解哪些維度項目對訂單有貢獻。例如，您可以看到對購買最有貢獻的前幾項行銷活動 (使用[追蹤代碼](../dimensions/tracking-code.md)維度)，或前幾名的內部搜尋詞彙 (使用 [eVar](../dimensions/evar.md))。

## 此量度的計算方式

此量度會計算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `purchase` 存在的點擊次數。

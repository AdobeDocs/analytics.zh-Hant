---
title: 訂購
description: 進行購買的次數。
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '91'
ht-degree: 100%

---

# 訂購

「訂單」量度會顯示您的網站上發生的購買事件總數。此量度對於電子商務網站的測量轉換至關重要。您可以將此量度與任何維度結合，了解哪些維度項目對訂單有貢獻。例如，您可以看到對購買最有貢獻的前幾項行銷活動 (使用[追蹤代碼](../dimensions/tracking-code.md)維度)，或前幾名的內部搜尋詞彙 (使用 [eVar](../dimensions/evar.md))。

## 此量度的計算方式

此量度會計算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `purchase` 存在的點擊次數。

---
title: 訂購
description: 進行購買的次數。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 80%

---


# 訂購

「訂單」量度會顯示您的網站上發生的購買事件總數。此量度對於電子商務網站的測量轉換至關重要。您可以將此度量與任何維度結合，以查看哪個維度項目促成了訂單。 例如，您可以看到對購買最有貢獻的前幾項行銷活動 (使用[追蹤代碼](../dimensions/tracking-code.md)維度)，或前幾名的內部搜尋詞彙 (使用 [eVar](../dimensions/evar.md))。

## 此量度的計算方式

此量度會計算 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `purchase` 存在的點擊次數。

---
title: 收入
description: 所有訂單中購買產品的貨幣金額。
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# 收入

「收入」量度會顯示所有訂單中購買產品的貨幣金額。 此量度對電子商務網站測量轉換至關重要。 您可以將此度量與任何維度結合，以瞭解哪些維度值對收入有貢獻。 例如，您可以看到排名最前的促銷活動(使用 [追蹤代碼維度](../dimensions/tracking-code.md) )或排名最前的內部搜尋詞(使用 [eVar](../dimensions/evar.md))。

## 此度量的計算方式

對於變數中存 `purchase` 在的每 [`events`](/help/implement/vars/page-vars/events/event-purchase.md) 個點擊，請總和變數中的「價格」欄 [`products`](/help/implement/vars/page-vars/products.md) 位。

如果頁面上的貨 [](/help/implement/vars/config-vars/currencycode.md) 幣與報表套裝的原生貨幣不同，此量度會依賴currencyCode變數。

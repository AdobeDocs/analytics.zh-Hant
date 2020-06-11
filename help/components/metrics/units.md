---
title: 件數
description: 所有訂單中購買的產品總數。
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# 件數

「件數」量度會顯示所有訂單中購買的產品總數。 此量度對電子商務網站測量轉換至關重要。 您可以將此度量與任何維度結合，以瞭解哪些維度值對購買多少產品有貢獻。 例如，您可以看到促成購買產品的熱門促銷活動(使用 [追蹤代碼維度](../dimensions/tracking-code.md) )或熱門內部搜尋詞(使用 [eVar](../dimensions/evar.md))。

## 此度量的計算方式

對於變數中存 `purchase` 在的每 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 個點擊，請總和變數中的「數量」 [`products`](/help/implement/vars/page-vars/products.md) 欄位。

## 比較訂單和件數

「訂 [購](orders.md) 」量度僅記錄購買事件數。 「件數」量度通常高於「訂購」，因為客戶可以購買多個產品。 在這些情況下，單個訂單存在多個單位。

如果您的訂單高於件數，Adobe建議您檢查實作的完整性。 您的變數在購買 `products` 時可能未正確設定，這通常是不想要的行為。

---
title: 收入
description: 所有訂單中購買產品的金額。
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 88%

---

# 收入

「收入」[量度](overview.md)會顯示所有訂單中購買產品的金額。 此量度對於電子商務網站的測量轉換至關重要。您可以將此量度與任何維度結合，了解哪些維度項目對收入有貢獻。例如，您可以看到前幾名的行銷活動 (使用[追蹤代碼](../dimensions/tracking-code.md)維度)，或前幾名的內部搜尋詞彙 (使用 [eVar](../dimensions/evar.md))。

## 此量度的計算方式

對於 [`events`](/help/implement/vars/page-vars/events/event-purchase.md) 變數中有 `purchase` 的每個點擊，加總 [`products`](/help/implement/vars/page-vars/products.md) 變數內的「價格」欄位。

如果頁面上的貨幣與報表套裝的原生貨幣不同，則此量度會依賴 [currencyCode](/help/implement/vars/config-vars/currencycode.md) 變數。

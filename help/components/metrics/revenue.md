---
title: 收入
description: 所有訂單中購買產品的金額。
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
TQID: https://experienceleague.adobe.com/GJsQWf7h-TihzyNUN6e3VGzOUNyxYD1esuvXet5LM1c
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 112
ht-degree: 74%

---

# 收入

「收入」[量度](overview.md)會顯示所有訂單中購買產品的金額。 此量度對於電子商務網站的測量轉換至關重要。 您可以將此量度與任何維度結合，瞭解哪些維度專案對收入有貢獻。 例如，您可以看到前幾名的行銷活動 (使用[追蹤代碼](../dimensions/tracking-code.md)維度)，或前幾名的內部搜尋詞彙 (使用 [eVar](../dimensions/evar.md))。

## 此量度的計算方式

對於 [`events`](/help/implement/vars/page-vars/events/event-purchase.md) 變數中有 `purchase` 的每個點擊，加總 [`products`](/help/implement/vars/page-vars/products.md) 變數內的「價格」欄位。

如果頁面上的貨幣與報表套裝的原生貨幣不同，則此量度會依賴 [currencyCode](/help/implement/vars/config-vars/currencycode.md) 變數。

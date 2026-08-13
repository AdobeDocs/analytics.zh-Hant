---
title: 單位數
description: 所有訂單中購買的產品總數。
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 80%

---

# 單位數

「件數」[量度](overview.md)會顯示所有訂單中購買的產品總數。 此量度對於電子商務網站的測量轉換至關重要。 您可以將此量度與任何維度結合，瞭解哪些維度專案促成了多少項產品的購買。 例如，您可以看到對產品購買最有貢獻的前幾項行銷活動 (使用[追蹤代碼](../dimensions/tracking-code.md)維度)，或前幾名的內部搜尋詞彙 (使用 [eVar](../dimensions/evar.md))。

## 此量度的計算方式

對於 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `purchase` 的每個點擊，加總 [`products`](/help/implement/vars/page-vars/products.md) 變數內的「數量」欄位。

## 比較訂單與件數

[訂單](orders.md)量度只會記錄購買事件的數量。 「件數」量度通常會高於「訂單」，因為客戶可購買多件產品。 在這種情況下，單一訂單可能包含多個件數。

如果您的訂單數高於件數，Adobe 建議您檢查實作的完整性。 有可能是您的 `products` 變數在購買時並未正確設定，這應該不是您要的行為。

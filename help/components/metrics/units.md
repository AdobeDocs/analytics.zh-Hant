---
title: 件數
description: 所有訂單中購買的產品總數。
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 80%

---

# 件數

「件數」[量度](overview.md)會顯示所有訂單中購買的產品總數。 此量度對於電子商務網站的測量轉換至關重要。您可以將此量度與任何維度結合，瞭解哪些維度專案促成了多少項產品的購買。 例如，您可以看到對產品購買最有貢獻的前幾項行銷活動 (使用[追蹤代碼](../dimensions/tracking-code.md)維度)，或前幾名的內部搜尋詞彙 (使用 [eVar](../dimensions/evar.md))。

## 此量度的計算方式

對於 [`events`](/help/implement/vars/page-vars/events/events-overview.md) 變數中有 `purchase` 的每個點擊，加總 [`products`](/help/implement/vars/page-vars/products.md) 變數內的「數量」欄位。

## 比較訂單與件數

[訂單](orders.md)量度只會記錄購買事件的數量。「件數」量度通常會高於「訂單」，因為客戶可購買多件產品。在這種情況下，單一訂單可能包含多個件數。

如果您的訂單數高於件數，Adobe 建議您檢查實作的完整性。有可能是您的 `products` 變數在購買時並未正確設定，這應該不是您要的行為。

---
title: 購買事件
description: 使用購買事件來收集「訂購」、「件數」和「收入」量度的資料。
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---

# 購買事件

購買事件是 `events` 變數中的值。對於想要收集網站產生之收入相關資料的組織來說，這個值非常有用。它與 [`products`](../products.md) 和 [`purchaseID`](../purchaseid.md) 等變數的相依性非常高。

當您設定購買事件時，它會影響下列量度：

* 「訂購」量度增加 1
* 「件數」量度以 `products` 變數中的產品數量為單位增加
* 「收入」量度會以 `products` 變數中的價格參數總和為單位增加

>[!NOTE]
>
>收入不會乘以數量欄位。以 `s.products="Womens;Socks;5;4.50"` 為例，傳入收入中的並不是 $22.50，而是 $4.50。請確認您的實施作業傳入的是所列數量的收入總額。例如：`s.products="Womens;Socks;5;22.50"`。

## 使用 Adobe Experience Platform 中的標記設定購買事件

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「事件」]區段，再將事件下拉式清單設定為[!UICONTROL 「購買」]。

其他相依變數 (例如 `products` 和 `purchaseID`) 在資料收集 UI 中並沒有專用欄位。 請依照這些變數的 AppMeasurement 語法，使用自訂程式碼編輯器。

## 在 AppMeasurement 和自訂程式碼編輯器中設定購買事件

購買事件是連同事件變數一起設定的字串。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 購買事件去重複化

當您引發購買事件時，Adobe 會檢查下列項目：

* 點擊是否包含 `purchaseID` 變數？若未包含，Adobe 會使用點擊中的資訊建立「臨時購買 ID」。這個臨時購買 ID 僅適用於點擊的訪客。系統會針對每個報表套裝的每個訪客 ID 儲存前 5 個臨時購買 ID。
* 臨時購買 ID 是否與最近 5 個儲存的臨時購買 ID 相符？如果符合，則會將影像要求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。
* 如果 `purchaseID` 變數已定義，它是否與報表套裝中針對所有訪客收集的任何值相符？如果符合，則會將影像要求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。

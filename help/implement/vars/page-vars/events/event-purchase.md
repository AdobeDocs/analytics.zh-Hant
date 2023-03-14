---
title: 購買事件
description: 使用購買事件來收集「訂購」、「件數」和「收入」量度的資料。
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 81%

---

# 購買事件

購買事件是 `events` 變數中的值。對於想要收集網站產生之收入相關資料的組織來說，這個值非常有用。它與 [`products`](../products.md) 和 [`purchaseID`](../purchaseid.md) 等變數的相依性非常高。

當您設定購買事件時，它會影響下列量度：

* 「訂購」量度增加 1
* 「件數」量度以 `products` 變數中的產品數量為單位增加
* 「收入」量度會以 `products` 變數中的價格參數總和為單位增加

>[!NOTE]
>
>收入不會乘以數量欄位。例如， `s.products="Womens;Socks;5;4.50"` 不會傳入$22.50;傳入$4.50。請確定您的實作傳入的是所列數量的收入總額。 例如，`s.products="Womens;Socks;5;22.50"`。

## 使用Web SDK設定購買事件

購買事件為 [已對應至Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在數個XDM欄位下：

* 訂單會對應到 `commerce.purchases.value`。
* 單位會對應到所有 `productListItems[].quantity` 欄位的總和。
* 營收會對應到所有 `productListItems[].priceTotal` 欄位的總和。

## 使用Adobe Analytics擴充功能設定購買事件

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「事件」]區段，再將事件下拉式清單設定為[!UICONTROL 「購買」]。

其他相依變數，例如 `products` 和 `purchaseID` Adobe Experience Platform Data Collection中的Analytics擴充功能中沒有專用欄位。 請依照這些變數的 AppMeasurement 語法，使用自訂程式碼編輯器。

## 在AppMeasurement和Analytics擴充功能自訂程式碼編輯器中設定購買事件

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

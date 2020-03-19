---
title: 購買事件
description: 使用購買事件來收集「訂購」、「件數」和「收入」度量的資料。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 購買事件

購買事件是變數中的 `events` 值。 此值對於想要收集其網站所產生收入相關資料的組織非常有用。 它嚴重依賴於變數 [`products`](../products.md) 和 [`purchaseID`](../purchaseid.md) 變數。

當您設定購買事件時，它會影響下列量度：

* 「訂購」量度以1為增量單位
* 「件數」量度以變數中的產品數為增 `products` 加
* 「收入」量度會依變數中的價格參數總和而增 `products` 加

## 在Adobe Experience Platform Launch中設定購買事件

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. 找到區 [!UICONTROL Events] 段，並將事件下拉式清單設為 [!UICONTROL purchase]。

其他相依變數( `products` 例如和 `purchaseID` )在Launch中沒有專用欄位。 請依照AppMeasurement語法，為這些變數使用自訂程式碼編輯器。

## 在AppMeasurement和Launch自訂代碼編輯器中設定購買事件

購買事件是設定為事件變數一部分的字串。

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## 購買事件重複消除

當您觸發購買事件時，Adobe會檢查下列項目：

* 點擊是否包含變 `purchaseID` 數？ 若否，Adobe會使用點擊中的資訊建立「臨時購買ID」。 這個臨時購買 ID 僅適用於點擊的訪客。前5個臨時購買ID會儲存為每個報表套裝的每個訪客ID。
* 臨時購買ID是否與前5個儲存的臨時購買ID中的任何一個相符？ 如果符合，則會將影像請求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。
* 如果已定 `purchaseID` 義變數，它是否符合所有訪客已在報表套裝中收集的任何值？ 如果符合，則會將影像請求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。

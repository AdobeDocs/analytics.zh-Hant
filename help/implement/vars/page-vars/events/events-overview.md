---
title: events
description: 設定事件變數，此變數可控制您網站上的大部分量度。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# events

維度和量度是報表的重要元件。 變 `events` 數負責收集您網站上許多量度的資料。

## Adobe Experience Platform Launch中的活動

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定事件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Events] section.

提供多項功能：

* 下拉式清單可讓您選取要包含的事件
* 用於序列化的選用文字欄位。 See [event serialization](event-serialization.md) for more information.
* 事件值的可選文字欄位。 您可以包含貨幣事件的貨幣，或非貨幣事件的整數，以增加多次。 例如，在下拉式清 `event1` 單下選取並在此欄位中 `10` 加入，在報表中 `event1` 會增加10。
* 新增其他事件的按鈕。 您在點擊中可包含的事件數目沒有合理限制。

## AppMeasurement和Launch自訂代碼編輯器中的s.events

變 `s.events` 數是字串，包含要包含在點擊中的逗號分隔事件清單。 此變數沒有位元組限制，因此不會截斷。 有效值包括:

* `event1` - `event1000`:自訂事件，視需要設定。 記錄您在組織解決方案設計檔案中使用每個事 [件的方式](../../../prepare/solution-design.md)。 可用事件的數目取決於您組織的Analytics合約。 大部分非舊合約的組織都有1000個可用的自訂事件。 如果您不確定可用的自訂事件有多少，請連絡您組織的客戶經理。
* `purchase`:將「訂購」量度遞增1，並使用變數中設 `products` 定的值來計算「件數」和「收入」。 如需詳 [細資訊](event-purchase.md) ，請參閱購買事件。
* `prodView`:遞增「產品檢視」量度。
* `scOpen`:遞增「購物車」量度。
* `scAdd`:遞增「購物車新增」量度。
* `scRemove`:遞增「購物車移除」量度。
* `scView`:遞增「購物車檢視」量度。
* `scCheckout`:遞增「結帳」量度。

> [!NOTE] 此變數區分大小寫。 避免誤用事件值，以確保資料收集的準確性。

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### 多次遞增計數器事件

您可視需要計算多次自訂事件。 為字串內的所需事件指派整數。 依預設，在報表套裝設定中建立的事件是計數器事件。

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

> [!NOTE] 計數器事件不支援貨幣或小數值。 使用貨幣事件或小數值的數值事件。

### 使用貨幣事件

您可以變更自訂事件，以使用貨幣而非整數。 如果報表套裝貨幣與變數不符，貨幣事件會自動轉換為報表套裝 `currencyCode` 的貨幣。 它們有助於計算運費、折扣或退款。 如果您想將事件歸因 `products` 於該產品，可在變數中設定貨幣事件。

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] 如果您在變數和變數中都設 `events` 定貨幣值 `products` ，則會使用中的貨 `events` 幣值。 請避免在變數和變數中設 `events` 定貨 `products` 幣值。

### 使用數值事件

您可以變更自訂事件，接受小數值，而非整數。 數值事件的行為與貨幣事件類似，但它們不使用貨幣轉換。 如果您想將事件歸因 `products` 於該產品，可在變數中設定數值事件。

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] 如果您在變數和變數中都設 `events` 定了數值 `products` ，則會使用 `events` 數值。 請避免在變數和變數中設 `events` 定數 `products` 值。

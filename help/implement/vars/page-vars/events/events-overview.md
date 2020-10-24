---
title: events
description: 設定事件變數，進而控制網站上大多數的量度。
translation-type: ht
source-git-commit: 2fd6e3b561d02bdbdd77b0be982614e765c870e2
workflow-type: ht
source-wordcount: '676'
ht-degree: 100%

---


# events

維度和量度是報表的重要元件。`events` 變數負責收集網站上許多量度的資料。事件通常會增加報表中的[量度](/help/components/metrics/overview.md)。

在實作事件之前，請務必在「報表套裝設定」的[「成功事件」](/help/admin/admin/c-success-events/success-event.md)底下建立和設定事件。如果您打算在連結追蹤點擊中使用自訂事件，請確定 [`linkTrackVars`](../../config-vars/linktrackvars.md) 和 [`linkTrackEvents`](../../config-vars/linktrackevents.md) 設定正確。

## Adobe Experience Platform Launch 中的事件

您可以在設定 Analytics 擴充功能 (全域變數) 時設定事件，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「事件」]區段。

您可以使用幾個功能：

* 下拉式清單可讓您選取要納入的事件
* 供序列化使用的選用文字欄位。如需詳細資訊，請參閱[事件序列化](event-serialization.md)。
* 供事件值使用的選用文字欄位。您可以納入貨幣來報告貨幣事件，或是納入整數來報告非貨幣事件，以便將值增加多次。例如，在下拉式清單下方選取 `event1`，並在此欄位中納入 `10`，可在報表中將 `event1` 增加 10。
* 新增其他事件的按鈕。一次點擊中可以納入的事件數目並沒有合理的限制。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.events

`s.events` 變數是字串，其中包含您要納入點擊中的逗號分隔事件清單。此變數沒有位元組限制，因此不會截斷。有效值包括：

* `event1` - `event1000`：自訂事件，視需要設定。請將每個事件的使用方式記錄在貴組織的[解決方案設計文件](../../../prepare/solution-design.md)中。可用事件的數目取決於貴組織的 Analytics 合約。簽訂非舊式合約的組織大多可以使用 1000 個自訂事件。如果您不確定有多少個自訂事件可供使用，請聯絡貴組織的客戶經理。
* `purchase`：將[訂單](/help/components/metrics/orders.md)量度增加 1，並使用在 `products` 變數中設定的值來計算[件數](/help/components/metrics/units.md)和[收入](/help/components/metrics/revenue.md)。如需詳細資訊，請參閱[購買事件](event-purchase.md)。
* `prodView`：增加[產品檢視](/help/components/metrics/product-views.md)量度。
* `scOpen`：增加[購物車](/help/components/metrics/carts.md)量度。
* `scAdd`：增加[購物車新增](/help/components/metrics/cart-additions.md)量度。
* `scRemove`：增加[購物車移除](/help/components/metrics/cart-removals.md)量度。
* `scView`：增加[購物車檢視](/help/components/metrics/cart-views.md)量度。
* `scCheckout`：增加[結帳](/help/components/metrics/checkouts.md)量度。

>[!NOTE]
>
>此變數會區分大小寫。請避免事件值的大小寫拼寫錯誤，確保資料彙集的準確性。

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### 多次增加計數器事件

您可以視需要多次計算自訂事件。將整數指派給字串內的所需事件。依預設，在報表套裝設定中建立的事件是計數器事件。

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>計數器事件不支援貨幣或小數值。請使用貨幣事件來報告貨幣，或使用數值事件來報告小數值。

### 使用貨幣事件

您可以變更自訂事件，使用貨幣來取代整數。如果報表套裝貨幣與 `currencyCode` 變數不符，貨幣事件會自動轉換為報表套裝的貨幣。這些事件有助於計算運費、折扣或退款。如果您想要將事件歸因限制為僅限該產品，可在 `products` 變數中設定貨幣事件。

在實作貨幣事件之前，請務必在「報表套裝設定」的[「成功事件」](/help/admin/admin/c-success-events/success-event.md)底下，將所需的事件設為「貨幣」。

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>如果您同時在 `events` 和 `products` 變數中設定貨幣值，系統會使用 `events` 中的貨幣值。請避免同時在 `events` 和 `products` 變數中設定貨幣值。

### 使用數值事件

您可以變更自訂事件，改為接受小數值而非整數。數值事件的行為與貨幣事件類似，但它們不使用貨幣轉換。如果您想要將事件歸因限制為僅限該產品，可在 `products` 變數中設定數值事件。

在實作數值事件之前，請務必在「報表套裝設定」的[「成功事件」](/help/admin/admin/c-success-events/success-event.md)底下，將所需的事件設為「數值」。

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>如果您同時在 `events` 和 `products` 變數中設定數值，系統會使用 `events` 中的數值。請避免同時在 `events` 和 `products` 變數中設定數值。

---
title: events
description: 設定事件變數，進而控制網站上大多數的量度。
feature: Appmeasurement Implementation
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 100%

---

# events

維度和量度是報表的重要元件。`events` 變數負責收集網站上許多量度的資料。事件通常會增加報表中的[量度](/help/components/metrics/overview.md)。

在實作事件之前，請務必在「報表套裝設定」的[「成功事件」](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)底下建立和設定事件。如果您打算在連結追蹤點擊中使用自訂事件，請確定 [`linkTrackVars`](../../config-vars/linktrackvars.md) 和 [`linkTrackEvents`](../../config-vars/linktrackevents.md) 設定正確。

## 使用 Web SDK 的事件

如果使用 [XDM 物件](/help/implement/aep-edge/xdm-var-mapping.md)，自訂事件會使用下列 XDM 欄位：

* 自訂事件 1-100 會對應到 `xdm._experience.analytics.event1to100.event1` - `xdm._experience.analytics.event1to100.event100`。
* 自訂事件 101-200 會對應到 `xdm._experience.analytics.event101to200.event100` - `xdm._experience.analytics.event101to200.event200`。
* 此模式每 100 個事件重複一次到 `xdm._experience.analytics.event901to1000.event901` - `xdm._experience.analytics.event901to1000.event1000`。 `eventx.value` 是用來指定要增加的數量。 `eventx.id` 是用來[序列化](event-serialization.md)。 
* 訂單會對應到 `xdm.commerce.purchases.value`。
* 單位會對應到所有 `productListItems[].quantity` 欄位的總和。
* 營收會對應到所有 `productListItems[].priceTotal` 欄位的總和。
* 產品視圖會對應到 `xdm.commerce.productViews.value`。
* 購物車會對應到 `xdm.commerce.productListOpens.value`。
* 購物車新增會對應到 `xdm.commerce.productListAdds.value`。
* 購物車移除會對應到 `xdm.commerce.productListRemovals.value`。
* 購物車檢視會對應到 `xdm.commerce.productListViews.value`。
* 結帳會對應到 `xdm.commerce.checkouts.value`。

>[!NOTE]
>
>如果在 `productListItems` 下設定事件 (例如 `productListItems._experience.analytics.event1.value`)，並且該事件尚未在此欄位中，則該事件會自動新增到此欄位中。

如果使用&#x200B;[**資料物件**](/help/implement/aep-edge/data-var-mapping.md)，所有事件會依照 AppMeasurement 語法使用 `data.__adobe.analytics.events`。如果您設定此欄位，XDM 物件中所設定的任何事件都會被覆寫，且不會傳送至 Adobe Analytics。

## 使用 Adobe Analytics 擴充功能的事件

您可以在設定 Analytics 擴充功能 (全域變數) 時設定事件，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設定為 Adobe Analytics，並將[!UICONTROL 「動作類型」]設定為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「事件」]區段。

您可以使用幾個功能：

* 讓您選取要包含哪些事件的下拉式清單
* 供序列化使用的選用文字欄位。如需詳細資訊，請參閱[事件序列化](event-serialization.md)。
* 供事件值使用的選用文字欄位。您可以納入貨幣來報告貨幣事件，或是納入整數來報告非貨幣事件，以便將值增加多次。例如，在下拉式清單中選取 `event1`，並在此欄位中包含 `10`，會讓報告中的 `event1` 增加 10。
* 新增其他事件的按鈕。您可以在合理的範圍內向單一規則新增任意數量的事件。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.events

`s.events` 變數是字串，其中含有要包含至點擊中的逗號分隔事件清單。此變數最多可使用 64k 位元組，實際上可讓單一點擊包含所需數量的事件。有效值包括：

* `event1` - `event1000`：自訂事件，視需要設定。請將每個事件的使用方式記錄在貴組織的[解決方案設計文件](../../../prepare/solution-design.md)中。可用事件的數目取決於貴組織的 Analytics 合約。簽訂非舊式合約的組織大多可以使用 1000 個自訂事件。如果您不確定可使用的自訂事件數量，請聯絡您的 Adobe 帳戶團隊。
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

在實作貨幣事件之前，請務必在「報表套裝設定」的[「成功事件」](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)底下，將所需的事件設為「貨幣」。

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

在實作數值事件之前，請務必在「報表套裝設定」的[「成功事件」](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)底下，將所需的事件設為「數值」。

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

---
title: 事件序列化
description: 協助您在網站上去除重複的量度。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 事件ID序列化

事件序列化為實作措施以防止重複事件進入 Analytics 報告的程序。若您不希望重新整理頁面的訪客誇大量度，請務必消除重複事件。

> [!NOTE]資料來源不支援事件序列化或去重複化。

## 設定事件序列化

您必須先在報表套裝設定中將事 [!UICONTROL Unique Event Recording] 件設 [!UICONTROL Use Event ID] 為「事件」。 See [Success Events](/help/admin/admin/c-success-events/success-event.md) in the Admin user guide.

使用事件ID時，重複資料消除會發生在以下級別：

* 每個變數都使用自己的表進行重複資料消除。 例如， `event1:ABC` 和 `event2:ABC` 都會計入報表。
* 重複資料消除會在所有訪客之間發生。 如果訪客A傳送 `event1:ABC` 後訪客B也傳送， `event1:ABC`Adobe會忽略訪客B的第二個例項。
* 重複資料消除不會過期。 如果訪客傳送 `event1:ABC` 後在2年後回來再傳送， `event1:ABC` Adobe會忽略第二個例項。

> [!TIP] 如果您想要去重複化事件， [`purchase`](event-purchase.md) 請改用變 [`purchaseID`](../purchaseid.md) 數。

## 使用Adobe Experience Platform Launch中的事件ID

您可以在設定Analytics擴充功能（全域變數）時設定事件ID欄位，或設定為規則中的動作。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. 找到區 [!UICONTROL Events] 段，其中每個事件都包含一 [!UICONTROL Event ID] 個欄位。

有效值是長度高達20個位元組的英數字元。

## 在AppMeasurement和Launch自訂代碼編輯器中使用事件ID

事件序列化是變數的一 `s.events` 部分。 使用字串中的冒號為每個事件指派ID。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

如果事件已啟用序列化，但不包含序列化ID，則一律會計算該事件。

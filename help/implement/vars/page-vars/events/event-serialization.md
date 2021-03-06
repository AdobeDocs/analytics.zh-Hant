---
title: 事件序列化
description: 協助您去除網站上重複的量度。
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 74%

---

# 事件 ID 序列化

事件序列化為實作措施以防止重複事件進入 Analytics 報告的程序。若您不希望量度因訪客重新整理頁面而不實膨脹，請務必去除重複事件。

>[!NOTE]
>
>資料來源不支援事件序列化或去重複化。

## 設定事件序列化

您必須先在報告套裝設定中將事件的[!UICONTROL 「獨特事件記錄」]設定設為[!UICONTROL 「使用事件 ID」]。請參閱「管理員使用指南」中的[成功事件](/help/admin/admin/c-success-events/success-event.md)。

使用事件 ID 時，去重複化會發生在以下層級：

* 每個變數都會使用自己的表格來進行去重複化。例如，`event1:ABC` 和 `event2:ABC` 都會計入報表。
* 去重複化會在所有訪客之間發生。如果訪客 A 傳送 `event1:ABC` 後訪客 B 也傳送 `event1:ABC`，Adobe 會忽略訪客 B 的第二個例項。
* 去重複化不會過期。如果訪客傳送 `event1:ABC` 後於 2 年後再回來傳送 `event1:ABC`，Adobe 會忽略第二個例項。

>[!TIP]
>
>如果您想要將 [`purchase`](event-purchase.md) 事件去重複化，請改用 [`purchaseID`](../purchaseid.md) 變數。

## 使用Web SDK使用事件ID

事件序列化是 [映射為Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 的 `id`。 完整的XDM路徑取決於要序列化的事件。

例如，如果要序列化「購物車添加」度量，請設定 `commerce.productListAdds.id` XDM欄位到所需的序列化值。 如果要序列化自定義事件20，請設定 `_experience.analytics.event1to100.event20` XDM欄位到所需的序列化值。

## 使用事件ID，使用Adobe Analytics擴展

您可以在設定 Analytics 擴充功能 (全域變數) 時設定事件 ID 欄位，或是在規則中將其設定為動作。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「事件」]區段，其中每個事件都包含[!UICONTROL 「事件 ID」]欄位。

有效值是長度最多 20 個位元組的英數字元。 如果輸入的值超過 20 個位元組，系統會截斷至前 20 個位元組。

## 在AppMeasurement和分析擴展自定義代碼編輯器中使用事件ID

事件序列化是 `s.events` 變數的一部分。在字串中使用冒號為每個事件指派 ID。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

如果事件已啟用序列化，但不包含序列化 ID，系統一律會計算該事件。

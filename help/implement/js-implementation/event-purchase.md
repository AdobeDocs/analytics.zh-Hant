---
description: 對於購買事件，會使用 Analytics 變數來擷取特定的購買資訊。s.purchaseID 變數可用來序列化事件 (對事件進行重複資料刪除)。
keywords: Analytics 實作
seo-description: 對於購買事件，會使用 Analytics 變數來擷取特定的購買資訊。s.purchaseID 變數可用來序列化事件 (對事件進行重複資料刪除)。
seo-title: 購買事件
solution: Analytics
title: 購買事件
topic: 開發人員和實作
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: e21bb18dd0d0eb13222c655091c3a87939a0351d

---


# 購買事件

對於購買事件，會使用 Analytics 變數來擷取特定的購買資訊。`s.purchaseID` 變數可用來序列化事件 (對事件進行重複資料刪除)。

如果呼叫購買事件但沒有 `purchaseID`，則會根據 `s.products` 和 `s.events` 變數自動產生一個唯一的 purchaseID。此自動產生的購買ID會儲存在訪客瀏覽器的本機Cookie值中，不會傳送給Adobe。 而手動定義的購買ID則會傳送至Adobe。 訪客（有無購買ID）最後5次購買會儲存在本機Cookie中。

當訪客進行購買時，會進行下列檢查:

* 此  購買ID符合5個Cookie值中的任何一個？ 如果符合，則會將影像請求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。
* 如果 `s.purchaseID` 已定義，它是否符合報表套裝中已收集的任何值？ 如果符合，則會將影像請求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。

您可以使用特定的伺服器端程式碼，產生內嵌於 HTML 來源中的唯一碼 (英數字元值)。通常會將訂單 ID 或類似的英數字元值用於此用途。若使用者重新整理頁面，此值不應變更。

## 語法

```js
s.purchaseID="12345678";
```

## 範例

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## 其他附註

* 請勿使用JavaScript隨機函式來產生數字，該數字會在每次載入頁面時產生唯一的數字。 Adobe建議使用資料層來儲存指定的購買ID。
* 唯一識別碼適用於所有工作階段的所有使用者。請確定所有購買ID都是真正唯一的。
* 有效值是長度高達20個字元的英數字元值。
* `s.purchaseID``s.events` 變數會序列化所有傳入變數   中的事件，並覆寫這些事件的序列化值。如果目前頁 [!UICONTROL 面上使用變數] ，請勿將事件 `s.purchaseID` 序列化用於任何事件。
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.

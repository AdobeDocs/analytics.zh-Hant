---
description: 對於購買事件，會使用 Analytics 變數來擷取特定的購買資訊。s.purchaseID 變數可用來序列化事件 (對事件進行重複資料刪除)。
keywords: Analytics 實施
seo-description: 對於購買事件，會使用 Analytics 變數來擷取特定的購買資訊。s.purchaseID 變數可用來序列化事件 (對事件進行重複資料刪除)。
seo-title: 購買事件
solution: Analytics
title: 購買事件
topic: 開發人員和實施
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 購買事件

對於購買事件，會使用 Analytics 變數來擷取特定的購買資訊。s.purchaseID 變數可用來序列化事件 (對事件進行重複資料刪除)。

*`purchaseID`* 限制為20個字元。*`purchaseID`* 變數會序列化所有傳入變數 [!UICONTROL s.events] 中的事件，並覆寫這些事件的序列化值。If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

如果呼叫購買事件但沒有 *`purchaseID`*，則會根據 *`s.products`* 和 *`s.events`變數自動產生一個唯一的 purchaseID。*&#x200B;這個自動產生的 *`purchaseID`會在訪客瀏覽器中儲存為本機 Cookie 值，且不會傳送給任何報表套裝表格。* Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

當訪客進行購買時，會進行下列檢查:

* 此 *`purchaseID`* 是否符合以上五個 Cookie 值? 如果符合，則會將影像請求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。
* *`purchaseID`* 如果已定義，是否符合報表套裝後端表格中的任何值？如果符合，則會將影像請求視為重複購買。所有轉換變數 (包括購買事件) 不會出現在報告中。
* 如果 *`purchaseID`* 相對於 Cookie 中的最後 5 個儲存值和報表套裝的 *`purchaseID`表格都未重複，則影像請求是唯一的且會納入報告中。*&#x200B;舉例說明，如果本機 Cookie 中已包含 5 項購買，將會覆寫最舊的項目。

您可以使用特定的伺服器端程式碼，產生內嵌於 HTML 來源中的唯一碼 (英數字元值)。通常會將訂單 ID 或類似的英數字元值用於此用途。若使用者重新整理頁面，此值不應變更。以下提供簡短範例 (請留意以粗體顯示的 *`purchaseID`* 程式碼): 

## 語法 {#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 
```

## 範例 {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## 其他附註 {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* 請確實使用伺服器端程式碼產生事件的唯一識別碼。請不要使用 JavaScript 隨機函數產生數字，因為它會在每次頁面載入時都產生唯一碼 (每個[!UICONTROL 例項]/[!UICONTROL 頁面檢視]都會計數)。

* 唯一識別碼適用於所有工作階段的所有使用者。因此，請確定此識別碼在使用者與工作階段間具有唯一性。例如，若訂單 ID 在 30 天之後重複，請加上訂單的日期，以確保[!UICONTROL 訂單 ID] 有足夠的唯一性。
* 序列化值可以是長度不超過 20個字元的英數字元值。此限制與 [!UICONTROL s.purchaseID] (若使用 G 程式碼，請將 s. 取代為 s_) 的限制相同。
* [!UICONTROL s.purchaseID] 變數會序列化所有傳入變數 [!UICONTROL s.events] 中的事件，並覆寫這些事件的序列化值。若現行頁面上使用了 [!UICONTROL s.purchaseID] 變數，請勿將[!UICONTROL 事件序列化]用於任何事件 (若使用 G 程式碼，請將 s. 取代為 s_)。


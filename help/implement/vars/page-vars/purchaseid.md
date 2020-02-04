---
title: purchaseID
description: 根據唯一的購買識別碼，去重複化點擊。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# purchaseID

此變 `purchaseID` 數可協助防止包含相同購買的點擊膨脹報表。 例如，如果訪客到達您的購買確認頁面，您通常會將交易所產生收入的相關資料傳送至Adobe。 如果使用者重新整理此頁面多次，或將頁面書籤設為稍後瀏覽，這些點擊可能會使報表膨脹。 變 `purchaseID` 數會在多個點擊具有相同購買ID時去除重複的量度。

當Adobe將點擊辨識為重複購買時，所有轉換資料（例如eVar和事件）都不會顯示在報表中。 在資料饋送中， `duplicate_purchase` 欄會設為 `1`。

購買ID會套用至所有訪客，且不會過期。 如果一個訪客設定了指定的購買ID，則另一位訪客在一年後設定了相同的購買ID，則會消除第二次購買的重複資料。

## Adobe Experience Platform Launch中的購買ID

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.purchaseID

變 `s.purchaseID` 數是包含購買唯一識別碼的字串。 它設定在與購買事件相同的點擊上。 僅使用英數字元填入此變數。

此變數最多可儲存20位元組；長度超過20個位元組的值會被截斷。 如果此截斷值與後續的截斷值相符，則會去除重複的後續點擊。

```js
s.purchaseID = "ABC123";
```

> [!NOTE] 請勿使用隨機函式來產生購買ID。 Adobe recommends using a [data layer](../../prepare/data-layer.md) to store a given purchase ID.

---
title: purchaseID
description: 根據唯一的購買識別碼去除重複點擊。
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '257'
ht-degree: 100%

---

# purchaseID

`purchaseID` 變數有助於防止包含相同購買操作的點擊導致報表不實膨脹。例如，如果訪客到達您的購買確認頁面，您通常會將交易產生的收入相關資料傳送至 Adobe。如果使用者重新整理此頁面多次，或是將頁面加入書籤以便稍後瀏覽，這些點擊可能會導致報表不實膨脹。當有多個點擊具有相同的購買 ID 時，`purchaseID` 變數會去除重複的量度。

當 Adobe 將點擊辨識為重複購買時，所有轉換資料 (如 eVar 和事件) 都不會顯示在報表中。在資料摘要中，`duplicate_purchase` 欄會設為 `1`。

購買 ID 會套用至所有訪客，而且不會過期。如果某位訪客設定了指定的購買 ID，另一位訪客在一年後設定了同一個購買 ID，則第二次購買的重複資料會遭到去除。

## 使用 Adobe Experience Platform 中的標記的購買 ID

資料收集 UI 中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和自訂程式碼編輯器中的 s.purchaseID

`s.purchaseID` 變數是包含唯一購買識別碼的字串。它設定在與購買事件相同的點擊上。填入此變數時，僅限使用英數字元。

此變數最多可儲存 20 個位元組；長度超過 20 個位元組的值會遭到截斷。如果此截斷值與後續的截斷值相符，後續點擊的重複資料會遭到去除。

```js
s.purchaseID = "ABC123";
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>請勿使用隨機函數來產生購買 ID。

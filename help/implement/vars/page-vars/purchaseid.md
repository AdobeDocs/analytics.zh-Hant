---
title: purchaseID
description: 根據唯一的購買識別碼去除重複點擊。
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 83%

---

# purchaseID

`purchaseID` 變數有助於防止包含相同購買操作的點擊導致報表不實膨脹。例如，如果訪客到達您的購買確認頁面，您通常會將交易產生的收入相關資料傳送至 Adobe。如果使用者重新整理此頁面多次，或是將頁面加入書籤以便稍後瀏覽，這些點擊可能會導致報表不實膨脹。當有多個點擊具有相同的購買 ID 時，`purchaseID` 變數會去除重複的量度。

當 Adobe 將點擊辨識為重複購買時，所有轉換資料 (如 eVar 和事件) 都不會顯示在報表中。在資料摘要中，`duplicate_purchase` 欄會設為 `1`。

購買ID會套用至所有訪客，並在37個月後過期。 如果某位訪客設定了指定的購買 ID，另一位訪客在一年後設定了同一個購買 ID，則第二次購買的重複資料會遭到去除。

## 使用Web SDK的購買ID

購買識別碼為 [已為Adobe Analytics進行對應](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=zh-Hant) 在XDM欄位下 `commerce.order.purchaseID`.

## 使用Adobe Analytics擴充功能的購買ID

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.purchaseID

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

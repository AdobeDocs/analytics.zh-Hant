---
description: 瞭解purchaseID變數，此變數可協助防止Adobe Analytics中出現重複購買。
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# purchaseID

The `purchaseID` variable is used to keep an order from being counted multiple times in reporting. Whenever the purchase event is used on your site, Adobe recommends using the `purchaseID` variable.

當訪客從您的網站購買項目時， `purchaseID` 通常會填入「感謝」或「訂購確認」頁面。 在引發 `purchaseID` 購買事件時，設定變數。 當 `purchaseID` 定義為唯一值時，轉換變數值只會計算該唯一購買ID的點擊。 定義這項 `purchaseID` 功能很有價值，因為訪客通常會為購買確認頁面加上書籤，以供其自行使用。 如果您的實作不使用， `purchaseID`則轉換資料（例如收入）可能會因訪客重新整理頁面而輕易膨脹。

除了購買資料外，所有轉換變數和事件都不會針對具有相同購買ID的點擊多次計算。

## 語法

變 `purchaseID` 數可包含任何英數字元值，最多20個位元組。 如果您設定的購買ID長度超過20個位元組，則會截斷值。

```js
s.purchaseID = "uniqueid";
```

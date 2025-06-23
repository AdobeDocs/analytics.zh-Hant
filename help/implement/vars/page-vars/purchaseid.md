---
title: purchaseID
description: 根據唯一的購買識別碼去除重複點擊。
feature: Appmeasurement Implementation
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 73%

---

# purchaseID

`purchaseID` 變數有助於防止包含相同購買操作的點擊導致報表不實膨脹。例如，如果訪客到達您的購買確認頁面，您通常會將交易產生的收入相關資料傳送至 Adobe。如果使用者重新整理此頁面多次，或是將頁面加入書籤以便稍後瀏覽，這些點擊可能會導致報表不實膨脹。當有多個點擊具有相同的購買 ID 時，`purchaseID` 變數會去除重複的量度。

當 Adobe 將點擊辨識為重複購買時，所有轉換資料 (如 eVar 和事件) 都不會顯示在報表中。在資料摘要中，`duplicate_purchase` 欄會設為 `1`。

購買ID會套用至所有訪客，並在37個月後過期。 如果某位訪客設定了指定的購買 ID，另一位訪客在一年後設定了同一個購買 ID，則第二次購買的重複資料會遭到去除。

## 使用網頁SDK的購買ID

購買ID會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.commerce.order.purchaseID`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.purchaseID`

## 使用Adobe Analytics擴充功能的購買ID

您可以在設定Analytics擴充功能（全域變數）時設定購買ID，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找到[!UICONTROL 購買ID]區段。

您可以將購買ID設為值或資料元素。 您也可以複製其他 Analytics 變數的值。

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

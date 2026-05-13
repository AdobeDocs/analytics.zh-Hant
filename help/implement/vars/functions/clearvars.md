---
title: clearVars
description: 清除例項物件的值。
feature: Appmeasurement Implementation
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
TQID: https://experienceleague.adobe.com/oZOgS1REUIwiLCwM1URlDy7rkpmeM59hrkOX7DBVVcE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 68%

---

# clearVars

某些實施 (如在單頁應用程式上) 要求在同一個頁面載入時傳送多個點擊。 使用 `clearVars()` 方法來清除變數值，使其不會存留至後續的點擊。

此方法不採用任何引數，也不會傳回任何值。 其唯一用途是清除例項物件的變數值。 此方法將下列元素設為 `undefined`：

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## 使用網頁SDK清除變數

當您使用網頁SDK傳送資料至Adobe時，所有XDM資料都會自動清除。

## 使用Adobe Analytics擴充功能清除變數

設定規則時設定「清除變數」動作。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下「+」圖示
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 清除變數]。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.clearVars()

將 Analytics 物件執行個體實體化之後，您就可以在實作中的任何地方呼叫 `s.clearVars()` 方法。

```js
s.clearVars();
```

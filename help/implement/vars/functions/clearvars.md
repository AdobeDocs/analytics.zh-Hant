---
title: clearVars
description: 會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# clearVars

某些實作（例如在單頁應用程式上）需要在相同頁面載入時傳送多個點擊。 使用方 `clearVars` 法清除變數值，使其不會持續存留至後續的點擊。

此方法不採用任何引數，也不返回任何值。 其唯一用途是從實例對象中清除變數值。 此方法將下列元素設為 `undefined`:

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

## Adobe Experience Platform Launch中的清除變數

設定規則時設定「清除變數」動作。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下，按一下「+」圖示
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設為Adobe Analytics，並將「動作類型 [!UICONTROL 」設為「] 清除變數」 。

## AppMeasurement和Launch自訂代碼編輯器中的s.clearVars()

在實例化Analytics物 `s.clearVars()` 件例項後，您可以在實作中的任何地方呼叫方法。

```js
s.clearVars();
```

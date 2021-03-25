---
title: clearVars
description: 從追蹤物件清除變數值。
translation-type: tm+mt
source-git-commit: f19be69832b0a2b723d825472e0eec1e44f89440
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 95%

---


# clearVars

某些實施 (如在單頁應用程式上) 要求在同一個頁面載入時傳送多個點擊。使用 `clearVars()` 方法來清除變數值，使其不會存留至後續的點擊。

此方法不採用任何引數，也不會傳回任何值。其唯一用途是清除例項物件的變數值。此方法將下列元素設為 `undefined`：

* `prop1` - `prop75`
* `eVar` -  `eVar250`
* `hier1` -  `hier5`
* `list1` -  `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Adobe Experience Platform Launch 中的清除變數

設定規則時設定「清除變數」動作。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下「+」圖示
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「清除變數」]。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.clearVars()

將 Analytics 物件例項實例化之後，您就可以在實施中的任何地方呼叫 `s.clearVars()` 方法。

```js
s.clearVars();
```

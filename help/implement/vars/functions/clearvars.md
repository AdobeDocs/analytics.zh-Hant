---
title: clearVars
description: 會清除例項物件中的下列值。此函數會移除元素 (即將其設為「未定義」)。
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '172'
ht-degree: 100%

---

# clearVars

某些實施 (如在單頁應用程式上) 要求在同一個頁面載入時傳送多個點擊。使用 `clearVars()` 方法來清除變數值，使其不會存留至後續的點擊。

此方法不採用任何引數，也不會傳回任何值。其唯一用途是清除例項物件的變數值。此方法將下列元素設為 `undefined`：

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

## 使用 Adobe Experience Platform 中的標記清除變數

設定規則時設定「清除變數」動作。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下「+」圖示
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「清除變數」]。

## AppMeasurement 和自訂程式碼編輯器中的 s.clearVars()

將 Analytics 物件執行個體實體化之後，您就可以在實作中的任何地方呼叫 `s.clearVars()` 方法。

```js
s.clearVars();
```

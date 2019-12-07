---
description: 預先定義的事件清單。
keywords: Analytics Implementation;event
title: 什麼是預先定義的事件?
topic: Developer and implementation
uuid: 4d0799ba-0f97-42c3-a620-36c03f9995da
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 什麼是預先定義的事件?

預先定義的事件清單。

| prodView | 只要訪客檢視產品，即發生成功事件。 |
|---|---|
| scView | 任何時候購物車被檢視即發生成功事件。 |
| scOpen | 任何時候訪客首次開啟購物車即發生成功事件。 |
| scAdd | 任何時候產品被新增至購物車內即發生成功事件。 |
| scRemove | 只要某項目從購物車中取出，即發生成功事件。 |
| scCheckout | 成功事件發生在結帳的第一個頁面上。 |
| purchase | 成功事件發生在結帳的最後一個頁面上 (包括「收入」、「訂購」及「件數」)。 |

當上述其中一個預先定義的事件發生時，即會增加一個事件例項。您可以在數個不同的報表中檢視與事件相關的度量。請參閱下列用來設定預先定義事件的程式碼範例。

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* 在上面的第一個範例中，*`scAdd`*&#x200B;為該事件的值。只要有項目新增至購物車，該事件即會增加。
* 在第二個範例中，同時擷取了兩個值。多個成功事件在相同的頁面上發生時，每個事件都會隨之增加。


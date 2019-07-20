---
description: 自訂事件可讓您定義所要追蹤的成功類型。
keywords: Analytics實作；自訂事件
seo-description: 自訂事件可讓您定義所要追蹤的成功類型。
seo-title: 甚麼是自訂事件？
solution: Analytics
title: 甚麼是自訂事件？
topic: 開發人員和實施
uuid: 8e78ba04-9b4c-4566-980c-c24 dd9 d82236
translation-type: tm+mt
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# 甚麼是自訂事件？

自訂事件可讓您定義所要追蹤的成功類型。

[!UICONTROL 自訂]事件與[!UICONTROL 預先定義]事件相仿，但前者可讓您定義自己的成功度量。For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. 藉由使用[!UICONTROL 自訂]事件，您可以追蹤註冊您的商務通訊的訪客數。[!UICONTROL 自訂]事件會遵循下方顯示的標準語法。

```js
s.events="event3"
```

上方的程式碼說明如何將事件指派給&#x200B;_事件_ 變數。If you do not modify the event name in the interface, _event3_ would display in the interface.

根據預設，成功事件會設定為&#x200B;_計數器_&#x200B;事件。計數器事件會計算成功事件的設定次數。使用某些成功事件時，事件會以自訂金額增加。These events can be set either as _numeric_ events or _currency_ events. 您可以在「管理控制台」中變更事件類型。

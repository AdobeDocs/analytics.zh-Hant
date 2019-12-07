---
description: 自訂事件可讓您定義所要追蹤的成功類型。
keywords: Analytics Implementation;custom event
title: 什麼是自訂事件?
topic: Developer and implementation
uuid: 8e78ba04-9b4c-4566-980c-c24dd9d82236
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 什麼是自訂事件?

自訂事件可讓您定義所要追蹤的成功類型。

[!UICONTROL 自訂]事件與[!UICONTROL 預先定義]事件相仿，但前者可讓您定義自己的成功度量。例如，若您有一份商務通訊，則您的成功事件可以是&#x200B;_註冊_。很明顯地，_註冊_&#x200B;並不屬於[!UICONTROL 預先定義]事件。藉由使用[!UICONTROL 自訂]事件，您可以追蹤註冊您的商務通訊的訪客數。[!UICONTROL 自訂]事件會遵循下方顯示的標準語法。

```js
s.events="event3"
```

上方的程式碼說明如何將事件指派給&#x200B;_events_ 變數。若您未修改介面中的事件名稱，則介面中將會顯示 _event3_。

根據預設，成功事件會設定為&#x200B;_計數器_&#x200B;事件。計數器事件會計算成功事件的設定次數。在使用某些成功事件時，事件必須以自訂數量做為增加單位。這些事件可設為&#x200B;_數值_&#x200B;事件或&#x200B;_貨幣_&#x200B;事件。您可以在管理控制台中變更事件類型。

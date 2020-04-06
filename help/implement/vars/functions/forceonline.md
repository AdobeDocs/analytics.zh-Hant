---
title: forceOnline
description: 手動設定 AppMeasurement 的線上狀態。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# forceOnline

`forceOnline()` 方法可讓您覆寫自動偵測到的 AppMeasurement 狀態。

>[!IMPORTANT] 只有在啟用時才使 [`trackOffline`](../config-vars/trackoffline.md) 用此方法。 在離線追蹤以外的情況下使用此函數可能會造成資料遺失。

AppMeasurement 會自動偵測裝置的線上狀態。您可以使用 `forceOnline()` 方法強迫 AppMeasurement 將點擊視為裝置上線。此方法不採用任何引數，也不會傳回任何值。其唯一用途是覆寫 AppMeasurement 中的線上狀態。

## Adobe Experience Platform Launch 中的強制上線

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.forceOnline()

將 Analytics 物件實例化之後，您就可以在實施中的任何地方呼叫 `s.forceOnline()` 方法。

```js
s.forceOnline();
```

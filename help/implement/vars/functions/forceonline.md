---
title: forceOnline
description: 手動設定AppMeasurement的線上狀態。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# forceOnline

此方 `forceOnline` 法可讓您覆寫自動偵測到的AppMeasurement狀態。

> [!IMPORTANT] 僅在啟用時使 `trackOffline` 用此函式。 在離線追蹤以外使用此函式可能會造成資料遺失。

AppMeasurement會自動偵測裝置的線上狀態。 您可以使用方 `forceOnline` 法強制AppMeasurement將點擊視為裝置線上。 此方法不採用任何引數，也不返回任何值。 其唯一用途是覆寫AppMeasurement中的線上狀態。

## 在Adobe Experience Platform Launch中強制線上

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.forceOnline()

在實例化Analytics物 `s.forceOnline()` 件後，您可以在實作中的任何地方呼叫方法。

```js
s.forceOnline();
```

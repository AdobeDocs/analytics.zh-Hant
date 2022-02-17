---
title: forceOffline
description: 手動設定 AppMeasurement 的線上狀態。
feature: Variables
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# 強制離線

`forceOffline()` 方法可讓您覆寫自動偵測到的 AppMeasurement 狀態。

>[!IMPORTANT]
>
> 使用此函數時 [`trackOffline`](../config-vars/trackoffline.md) 必須已啟用。在離線追蹤以外的情況下使用此函數可能會造成資料遺失。

AppMeasurement 會自動偵測裝置的線上狀態。您可以使用 `forceOffline()` 方法強迫 AppMeasurement 將點擊視為裝置離線。此方法不採用任何引數，也不會傳回任何值。其唯一用途是覆寫 AppMeasurement 中的線上狀態。

## 使用 Adobe Experience Platform 中的標記的強制離線

資料收集 UI 中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和自訂程式碼編輯器中的 s.forceOffline()

將 Analytics 物件實體化之後，您就可以在實作中的任何地方呼叫 `s.forceOffline()` 方法。

```js
s.forceOffline();
```

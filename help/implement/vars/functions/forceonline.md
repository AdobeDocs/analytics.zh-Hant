---
title: forceOnline
description: 手動設定 AppMeasurement 的線上狀態。
feature: Variables
exl-id: 318408bf-bec6-49aa-a762-9d2eebab233e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 70%

---

# 強制線上

`forceOnline()` 方法可讓您覆寫自動偵測到的 AppMeasurement 狀態。

>[!WARNING]
>
>只能在啟用了 [`trackOffline`](../config-vars/trackoffline.md) 時使用此方法。 在離線追蹤以外的情況下使用此函數可能會造成資料遺失。

AppMeasurement 會自動偵測裝置的線上狀態。您可以使用 `forceOnline()` 方法強迫 AppMeasurement 將點擊視為裝置上線。此方法不採用任何引數，也不會傳回任何值。其唯一用途是覆寫 AppMeasurement 中的線上狀態。

## 使用Web SDK強制聯機

Web SDK不支援離線跟蹤。

## 使用Adobe Analytics分機強制聯機

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement中的s.forceOnline()和Analytics擴展自定義代碼編輯器

將 Analytics 物件實體化之後，您就可以在實作中的任何地方呼叫 `s.forceOnline()` 方法。

```js
s.forceOnline();
```

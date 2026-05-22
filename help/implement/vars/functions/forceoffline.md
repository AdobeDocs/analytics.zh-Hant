---
title: forceOffline
description: 手動設定 AppMeasurement 的線上狀態。
feature: Appmeasurement Implementation
exl-id: 2e48bdf6-7de7-4976-86dd-ef3d558769c7
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/1Y2HmD9-Xu5SjlrVIuJkcNtWxvDh7XNNqvSiwFwHtlY'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 157
ht-degree: 80%

---

# forceOffline

`forceOffline()` 方法可讓您覆寫自動偵測到的 AppMeasurement 狀態。

>[!WARNING]
>
>使用此函數時 [`trackOffline`](../config-vars/trackoffline.md) 必須已啟用。 在離線追蹤以外的情況下使用此函數可能會造成資料遺失。

AppMeasurement 會自動偵測裝置的線上狀態。 您可以使用 `forceOffline()` 方法強迫 AppMeasurement 將點擊視為裝置離線。 此方法不採用任何引數，也不會傳回任何值。 其唯一用途是覆寫 AppMeasurement 中的線上狀態。

## 使用網頁SDK強制離線

網頁SDK不支援離線追蹤。

## 使用Adobe Analytics擴充功能強制離線

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.forceOffline()

將 Analytics 物件實體化之後，您就可以在實作中的任何地方呼叫 `s.forceOffline()` 方法。

```js
s.forceOffline();
```

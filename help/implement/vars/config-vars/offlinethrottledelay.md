---
title: offlineThrottleDelay
description: 建立裝置重新上線時的點擊頻率。
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 83%

---

# offlineThrottleDelay

離線追蹤是在 Adobe Analytics 中收集資料的選用方式。如果訪客中斷網際網路連線但繼續瀏覽您的網站，點擊會儲存在離線佇列中，直到裝置重新連接網際網路為止。離線追蹤大多用於行動應用程式。

當裝置重新上線時，儲存在裝置上的所有點擊都會傳送至 Adobe 資料收集伺服器。大量佇列的點擊可能會影響舊裝置的效能。使用 `offlineThrottleDelay` 變數來建立佇列點擊傳送至 Adobe 的頻率。

## 使用網頁SDK的離線節流延遲

網頁SDK不支援離線追蹤。

## 使用Adobe Analytics擴充功能的離線節流延遲

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.offlineThrottleDelay

`s.offlineThrottleDelay` 變數是整數，代表 AppMeasurement 在多次傳送佇列點擊之間等待的毫秒數。其預設值為 `0`，表示所有佇列點擊會一次傳送。如果 `trackOffline` 是 `false`，此變數不會產生任何效用。

```js
s.offlineThrottleDelay = 500;
```

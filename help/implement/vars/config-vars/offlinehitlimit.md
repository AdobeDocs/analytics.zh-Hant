---
title: offlineHitLimit
description: 決定離線追蹤佇列的點擊數上限。
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 88%

---

# offlineHitLimit

離線追蹤是在 Adobe Analytics 中收集資料的選用方式。如果訪客中斷網際網路連線但繼續瀏覽您的網站，點擊會儲存在離線佇列中，直到裝置重新連接網際網路為止。離線追蹤大多用於行動應用程式。

`offlineHitLimit` 變數會將裝置本機儲存的點擊數加上上限。此變數僅適用於啟用 [`trackOffline`](trackoffline.md) 的情況。

## 使用Adobe Analytics擴充功能的離線點擊限制

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.offlineHitLimit

`s.offlineHitLimit` 變數是整數，代表裝置離線時儲存的最大點擊數。如果未定義此變數，裝置離線時儲存的點擊數將沒有限制。

```js
s.offlineHitLimit = 100;
```

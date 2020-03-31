---
title: offlineThrottleDelay
description: 建立裝置重新上線時的點擊頻率。
translation-type: ht
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

離線追蹤是在 Adobe Analytics 中收集資料的選用方式。如果訪客中斷網際網路連線但繼續瀏覽您的網站，點擊會儲存在離線佇列中，直到裝置重新連接網際網路為止。離線追蹤大多用於行動應用程式。

當裝置重新上線時，儲存在裝置上的所有點擊都會傳送至 Adobe 資料收集伺服器。大量佇列的點擊可能會影響舊裝置的效能。使用 `offlineThrottleDelay` 變數來建立佇列點擊傳送至 Adobe 的頻率。

## Adobe Experience Platform Launch 中的離線節流延遲

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.offlineThrottleDelay

`s.offlineThrottleDelay` 變數是整數，代表 AppMeasurement 在多次傳送佇列點擊之間等待的毫秒數。其預設值為 `0`，表示所有佇列點擊會一次傳送。如果 `trackOffline` 是 `false`，此變數不會產生任何效用。

```js
s.offlineThrottleDelay = 500;
```

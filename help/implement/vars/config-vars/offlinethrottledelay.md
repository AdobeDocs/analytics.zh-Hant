---
title: offlineThrottleDelay
description: 建立裝置重新上線時的點擊頻率。
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

離線追蹤是在Adobe Analytics中收集資料的選用方式。 如果訪客中斷網際網路連線但繼續瀏覽您的網站，則會將點擊儲存在離線佇列中，直到裝置重新連線至網際網路為止。 離線追蹤主要用於行動應用程式。

當裝置重新連線時，儲存在裝置上的所有點擊都會傳送至Adobe資料收集伺服器。 大量佇列的點擊可能會影響舊裝置的效能。 使用變 `offlineThrottleDelay` 數來建立佇列點擊傳送至Adobe的頻率。

## Adobe Experience Platform Launch中的離線限制延遲

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.offlineThrottleDelay

變 `s.offlineThrottleDelay` 數是一個整數，代表AppMeasurement在傳送佇列的點擊之間等待的毫秒數。 其預設值為 `0`，表示所有佇列的點擊都會一次傳送。 如果 `trackOffline` 是 `false`，則此變數不會執行任何動作。

```js
s.offlineThrottleDelay = 500;
```

---
title: offlineHitLimit
description: 確定離線追蹤佇列的點擊數上限。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

離線追蹤是在Adobe Analytics中收集資料的選用方式。 如果訪客中斷網際網路連線但繼續瀏覽您的網站，則會將點擊儲存在離線佇列中，直到裝置重新連線至網際網路為止。 離線追蹤主要用於行動應用程式。

變 `offlineHitLimit` 數會在裝置本機儲存的點擊數上加上上限。 此變數僅在啟用時 [`trackOffline`](trackoffline.md) 有效。

## Adobe Experience Platform Launch中的離線點擊限制

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.offlineHitLimit

變 `s.offlineHitLimit` 數是整數，代表裝置離線時儲存的最大點擊數。 如果未定義此變數，裝置離線時儲存的點擊數目沒有限制。

```js
s.offlineHitLimit = 100;
```

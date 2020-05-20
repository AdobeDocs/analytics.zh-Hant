---
title: offlineHitLimit
description: 決定離線追蹤佇列的點擊數上限。
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

離線追蹤是在 Adobe Analytics 中收集資料的選用方式。如果訪客中斷網際網路連線但繼續瀏覽您的網站，點擊會儲存在離線佇列中，直到裝置重新連接網際網路為止。離線追蹤大多用於行動應用程式。

`offlineHitLimit` 變數會將裝置本機儲存的點擊數加上上限。此變數僅適用於啟用 [`trackOffline`](trackoffline.md) 的情況。

## Adobe Experience Platform Launch 中的離線點擊限制

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.offlineHitLimit

`s.offlineHitLimit` 變數是整數，代表裝置離線時儲存的最大點擊數。如果未定義此變數，裝置離線時儲存的點擊數將沒有限制。

```js
s.offlineHitLimit = 100;
```

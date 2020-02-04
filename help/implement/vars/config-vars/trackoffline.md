---
title: trackOffline
description: 啟用或停用離線追蹤，這會變更AppMeasurement收集資料的方式。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackOffline

離線追蹤是在Adobe Analytics中收集資料的選用方式。 如果訪客中斷網際網路連線但繼續瀏覽您的網站，則會將點擊儲存在離線佇列中，直到裝置重新連線至網際網路為止。 離線追蹤主要用於行動應用程式。

變 `trackOffline` 數會決定您是否要在實作中使用離線追蹤。

> [!IMPORTANT] 您必須先設定報表套裝接受時間戳記點擊，才能啟用此變數。 如果報表套裝不接受時間戳記點擊，且此變數已啟用，則該資料會遺失且無法復原。

啟用後，AppMeasurement會使用下列程式將資料傳送至Adobe:

* 在編譯影像請求時，包括時間戳查詢字串參數。
* 如果裝置無法到達Adobe資料收集伺服器，則點擊會儲存在裝置本機。
* 在每次後續點擊期間，AppMeasurement都會嘗試傳送影像要求至Adobe。
   * 如果無法到達Adobe資料收集伺服器，則會將點擊新增至裝置上的佇列。
   * 如果它可觸及Adobe資料收集伺服器，則會傳送裝置離線時的點擊和點擊佇列。

## 在Adobe Experience Platform Launch中追蹤離線

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.trackOffline

變 `s.trackOffline` 數是布林值，可啟用或停用離線追蹤。 Its default value is `false`. 如果您要啟 `true` 用離線追蹤，請將此值設定為。

```js
s.trackOffline = true;
```

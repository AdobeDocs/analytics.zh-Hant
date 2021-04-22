---
title: trackOffline
description: 啟用或停用離線追蹤，變更 AppMeasurement 收集資料的方式。
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '264'
ht-degree: 100%

---

# trackOffline

離線追蹤是在 Adobe Analytics 中收集資料的選用方式。如果訪客中斷網際網路連線但繼續瀏覽您的網站，點擊會儲存在離線佇列中，直到裝置重新連接網際網路為止。離線追蹤大多用於行動應用程式。

`trackOffline` 變數決定您是否要在實施中使用離線追蹤。

>[!IMPORTANT]
>
>啟用此變數之前，您必須先設定報告套裝接受時間戳記點擊。如果報表套裝不接受時間戳記點擊，但此變數已啟用，該資料會遺失且無法復原。

啟用後，AppMeasurement 會使用下列程序將資料傳送至 Adobe：

* 在編譯影像要求時，納入時間戳查詢字串參數。
* 如果裝置無法連接 Adobe 資料收集伺服器，點擊會儲存在裝置本機。
* 在後續每次點擊期間，AppMeasurement 都會嘗試將影像要求傳送至 Adobe。
   * 如果無法連接 Adobe 資料收集伺服器，點擊會新增到裝置上的佇列。
   * 如果它可以連接 Adobe 資料收集伺服器，便會傳送裝置離線時的點擊和點擊佇列。

## Adobe Experience Platform Launch 中的離線追蹤

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackOffline

`s.trackOffline` 是布林值，可啟用或停用離線追蹤。其預設值為 `false`。如果您要啟用離線追蹤，請將此值設定為 `true`。

```js
s.trackOffline = true;
```

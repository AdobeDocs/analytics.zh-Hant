---
title: offlineHitLimit
description: 決定離線追蹤佇列的點擊數上限。
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-uvCAqUO0A-7XjlemN4XwHXVG9DFK-UoVTW77up9-AY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 39%

---

# offlineHitLimit

離線追蹤是在 Adobe Analytics 中收集資料的選用方式。 如果訪客中斷網際網路連線但繼續瀏覽您的網站，點選會儲存在離線佇列中，直到裝置重新連線到網際網路為止。 離線追蹤大多用於行動應用程式。

`offlineHitLimit` 變數會將裝置本機儲存的點擊數加上上限。 此變數僅適用於啟用 [`trackOffline`](trackoffline.md) 的情況。

## 使用網頁SDK的離線點選限制

網頁SDK不支援離線追蹤。

## 使用Adobe Analytics擴充功能的離線點選限制

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.offlineHitLimit

`s.offlineHitLimit`變數是整數，代表裝置離線時儲存的最大點選數。 如果此變數未定義，其預設值為`10`。 您可以將其設為任何整數值。 設定高值時，請留意訪客瀏覽器中的本機儲存上限。 此限制通常為5 - 10 MB。

```js
s.offlineHitLimit = 100;
```

---
title: offlineHitLimit
description: 決定離線追蹤佇列的點擊數上限。
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 39%

---

# offlineHitLimit

離線追蹤是在 Adobe Analytics 中收集資料的選用方式。如果訪客中斷網際網路連線但繼續瀏覽您的網站，點選會儲存在離線佇列中，直到裝置重新連線到網際網路為止。 離線追蹤大多用於行動應用程式。

`offlineHitLimit` 變數會將裝置本機儲存的點擊數加上上限。此變數僅適用於啟用 [`trackOffline`](trackoffline.md) 的情況。

## 使用網頁SDK的離線點選限制

網頁SDK不支援離線追蹤。

## 使用Adobe Analytics擴充功能的離線點選限制

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.offlineHitLimit

`s.offlineHitLimit`變數是整數，代表裝置離線時儲存的最大點選數。 如果此變數未定義，其預設值為`10`。 您可以將其設為任何整數值。 設定高值時，請留意訪客瀏覽器中的本機儲存上限。 此限制通常為5 - 10 MB。

```js
s.offlineHitLimit = 100;
```

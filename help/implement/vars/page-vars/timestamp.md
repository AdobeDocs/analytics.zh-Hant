---
title: 時間戳記
description: 手動設定點擊的時間戳記。
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jEsdtS45c6ZDxjmCgVciTOjXJVAxzjbESObgPucrIhk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 82%

---

# 時間戳記

針對啟用時間戳記的報表套裝，`timestamp` 變數能手動設定點擊的時間戳記。

>[!WARNING]
>
>如果您的報表套裝未明確設定為接受時間戳記點擊，請勿使用此變數。 對於不支援時間戳記點擊的報表套裝，AppMeasurement 會自動設定點擊時間。 如果您將包含此變數的點擊傳送到不支援時間戳記的報表套裝，該資料會永久遺失。

## 使用網頁SDK的時間戳記

XDM欄位`xdm.timestamp`下的Adobe Analytics[&#128279;](/help/implement/aep-edge/xdm-var-mapping.md)時間戳記為對應。 此欄位僅支援Unix時間。

## 使用Adobe Analytics擴充功能的時間戳記

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.timestamp

`s.timestamp` 變數是包含點擊日期和時間的字串。 有效的時間戳記格式包括[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)和[Unix時間](https://en.wikipedia.org/wiki/Unix_time) （以秒為單位）。

```js
// Timestamp using ISO 8601
s.timestamp = "2024-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601 值

以 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 表示的日期和時間，可能會採用數種不同的形式。 Adobe 不支援 ISO 8601 的所有功能。

* 日期與時間都必須提供，使用 `T` 分隔。
* 小時和分鐘都是必要值；秒數是選用值，不過建議提供。
* 不支援週日期和序數日期。
* 日期可採用標準或延伸格式。 例如 `2024-01-01T00:00:00Z` 和 `20240101T000000Z` 都有效。
* 技術上來說，分數形式的分鐘和秒是有效值，不過 Adobe 會忽略分數部分。
* 支援的標準和延伸格式的時區。

以下是 `timestamp` 變數中的有效範例 ISO 8601 值：

```text
2024-01-01T00:00:00+00:00
2024-01-01T00:00:00Z
2024-01-01T00:00:00
2024-01-01T00:00
20240101T000000+0000
20240101T000000Z
20240101T000000
20240101T0000
```

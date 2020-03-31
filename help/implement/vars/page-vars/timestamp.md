---
title: timestamp
description: 手動設定點擊的時間戳記。
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# timestamp

針對啟用時間戳記的報表套裝，`timestamp` 變數能手動設定點擊的時間戳記。

> [!WARNING] 如果您的報表套裝未明確設定為接受時間戳記點擊，請勿使用此變數。對於不支援時間戳記點擊的報表套裝，AppMeasurement 會自動設定點擊時間。如果您將包含此變數的點擊傳送到不支援時間戳記的報表套裝，該資料會永久遺失。

## Adobe Experience Platform Launch 中的時間戳記

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.timestamp

`s.timestamp` 變數是包含點擊日期和時間的字串。有效的時間戳記格式包括 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 和 [Unix 時間](https://en.wikipedia.org/wiki/Unix_time)。

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601 值

以 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 表示的日期和時間，可能會採用數種不同的形式。Adobe 不支援 ISO 8601 的所有功能。

* 日期與時間都必須提供，使用 `T` 分隔。
* 小時和分鐘都是必要值；秒數是選用值，不過建議提供。
* 不支援週日期和序數日期。
* 日期可採用標準或延伸格式。例如 `2020-01-01T00:00:00Z` 和 `20200101T000000Z` 都有效。
* 技術上來說，分數形式的分鐘和秒是有效值，不過 Adobe 會忽略分數部分。
* 支援的標準和延伸格式的時區。

以下是 `timestamp` 變數中的有效範例 ISO 8601 值：

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```

---
title: timestamp
description: 手動設定點擊的時間戳記。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# timestamp

此變 `timestamp` 數會手動設定啟用時間戳記之報表套裝的點擊時間戳記。

> [!WARNING] 如果您的報表套裝未明確設定為接受時間戳記點擊，請勿使用此變數。 AppMeasurement會自動為不支援時間戳記點擊的報表套裝設定點擊時間。 如果您將此變數傳送點擊至不支援時間戳記的報表套裝，該資料會永久遺失。

## Adobe Experience Platform Launch中的時間戳記

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.timestamp

變 `s.timestamp` 數是包含點擊日期和時間的字串。 有效的時間戳記格 [式包括ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)[和Unix時間](https://en.wikipedia.org/wiki/Unix_time)。

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

## ISO 8601值

在 [ISO 8601中表示的日期和時間](https://en.wikipedia.org/wiki/ISO_8601) ，可採用數種不同的形式。 Adobe不支援ISO 8601的所有功能。

* Both the date and time must be provided, separated by `T`.
* 需要數小時和數分鐘；秒數是可選的，但建議使用。
* 不支援週日期和序數日期。
* 日期可採用標準或延伸格式。 例如， `2020-01-01T00:00:00Z` 和 `20200101T000000Z` 都有效。
* 分數分鐘和秒數在技術上有效，但Adobe會忽略分數。
* 標準和擴充格式支援時區。

以下是變數中的有效範例ISO 8601 `timestamp` 值：

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

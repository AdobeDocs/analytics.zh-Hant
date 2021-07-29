---
title: Util.cookieWrite
description: 將值寫入 Cookie。
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 82%

---

# Util.cookieWrite

Cookie可以儲存和擷取相同網域上各頁面的資訊。使用 `Util.cookieWrite()` 方法可設定 Cookie 的值。您可以使用 [`Util.cookieRead()`](util-cookieread.md) 方法來擷取以 `Util.cookieWrite()` 設定的值。

## 在Adobe Experience Platform中使用標籤設定Cookie

資料收集UI不提供在介面中設定Cookie的功能。 依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 自訂程式碼編輯器中的 s.Util.cookieWrite()

呼叫 `s.Util.cookieWrite()` 方法將 Cookie 設定為所需的值。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

有選用的第三個引數可使用，其決定 Cookie 的過期時間。使用 `s.Util.cookieWrite()` 設定的 Cookie，預設會在瀏覽器作業結束時過期。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 範例

您可以在成功寫入 Cookie 時將變數實例化。此變數為布林值。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```

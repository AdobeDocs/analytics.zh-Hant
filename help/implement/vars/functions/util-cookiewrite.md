---
title: Util.cookieWrite
description: 寫入Cookie的值。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieWrite

Cookie可以儲存和擷取相同網域上各頁面的資訊。 使用 `Util.cookieWrite()` 方法將值設為Cookie。 您可以使用方 [`Util.cookieRead()`](util-cookieread.md) 法來檢索使用設定的值 `Util.cookieWrite()`。

## 在Adobe Experience Platform Launch中設定Cookie

Launch無法在介面中設定Cookie。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.Util.cookieWrite()

呼叫方 `s.Util.cookieWrite()` 法，將Cookie設定為所需值。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

有可選的第三個引數可決定Cookie的過期時間。 使用設定 `s.Util.cookieWrite()` 的Cookie預設會在瀏覽器作業結束時過期。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 範例

您可以在成功寫入Cookie時執行個體化變數。 此變數為布林值。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```

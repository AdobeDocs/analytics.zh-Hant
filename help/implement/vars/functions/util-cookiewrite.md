---
title: Util.cookieWrite
description: 將值寫入 Cookie。
feature: Appmeasurement Implementation
exl-id: 079dbe50-5568-467b-a67c-f44481a4a20b
role: Admin, Developer
TQID: https://experienceleague.adobe.com/lMhRsrz97N5w8oXBIfwm1FjuVb6epmGeeP3LeO4zXQI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 70%

---

# Util.cookieWrite

Cookie可以儲存和擷取相同網域上各頁面的資訊。 使用 `Util.cookieWrite()` 方法可設定 Cookie 的值。 您可以使用 [`Util.cookieRead()`](util-cookieread.md) 方法來擷取以 `Util.cookieWrite()` 設定的值。

## 使用Adobe Analytics擴充功能和Web SDK擴充功能設定Cookie

Adobe Experience Platform資料收集不提供在介面中設定Cookie的功能。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.Util.cookieWrite()

呼叫 `s.Util.cookieWrite()` 方法將 Cookie 設定為所需的值。

```js
s.Util.cookieWrite("example_cookie","Example cookie value")
```

有選用的第三個引數可使用，其決定 Cookie 的過期時間。 使用 `s.Util.cookieWrite()` 設定的 Cookie，預設會在瀏覽器作業結束時過期。

```js
// Set a cookie with an expiration 6 months from now
var cookieDate = new Date();
cookieDate.setMonth(cookieDate.getMonth() + 6);
s.Util.cookieWrite("example_cookie","Example 6-month cookie",cookieDate);
```

## 範例

您可以在成功寫入 Cookie 時將變數實例化。 此變數為布林值。

```js
var success = s.Util.cookieWrite("example_cookie","Example cookie value");
if (success) {
  console.log("Cookie written successfully");
} else {
  console.log("Cookie write failed");
}
```

---
title: linkURL
description: 覆寫 AppMeasurement 在連結追蹤呼叫中使用的自動產生連結 URL。
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkURL

每當連結追蹤呼叫傳送至 Adobe 時，資料收集伺服器都會自動偵測 URL。使用 `linkURL` 變數來覆寫偵測到的 URL。

## Adobe Experience Platform Launch 中的連結 URL

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.linkURL

`s.linkURL` 變數是字串，包含點按連結時瀏覽器的 URL。此變數不會填入報表中任何可用的維度。

```js
s.linkURL = "https://example.com";
```

如果您未設定連結追蹤呼叫的 [`linkName`](linkname.md) 變數，系統會改用 `linkURL` 變數。

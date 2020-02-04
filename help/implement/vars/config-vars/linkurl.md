---
title: linkURL
description: 覆寫AppMeasurement在連結追蹤呼叫中使用的自動產生的連結URL。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkURL

每當連結追蹤呼叫傳送至Adobe時，資料收集伺服器都會自動偵測URL。 使用變 `linkURL` 數來覆寫偵測到的URL。

## Adobe Experience Platform Launch中的連結URL

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.linkURL

變 `s.linkURL` 數是字串，包含點按連結時瀏覽器的URL。 此變數不會填入報表中任何可用的維度。

```js
s.linkURL = "https://example.com";
```

如果未 `linkName` 為連結追蹤呼叫設定變數，則會改 `linkURL` 用變數。

---
title: linkURL
description: 覆寫 AppMeasurement 在連結追蹤呼叫中使用的自動產生連結 URL。
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '115'
ht-degree: 100%

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

如果 [tl()](../functions/tl-method.md) 方法的第三個引數未經設定，則會改用 `linkURL` 變數。

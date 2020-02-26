---
title: useLinkTrackSessionStorage
description: 將連結追蹤資料儲存在工作階段儲存中，而非Cookie。
translation-type: tm+mt
source-git-commit: e1a08ecd3d5eb41bce7ca91027249871c3b5b22f

---


# useLinkTrackSessionStorage

如果您的組織使用連結追蹤，AppMeasurement會使用 `s_sq` Cookie在點擊之間傳遞資訊。 某些網站設定會與此Cookie發生衝突。 如果您想要使用瀏覽器作業儲存來追蹤連結和Activity map資料，而非使用Cookie，請啟用此變數。

使用瀏覽器的作業儲存空間進行連結追蹤有幾項限制：

* 會話儲存在協定之間無效。 例如，您有一個頁面透過HTTP提供，而下一個頁面則透過HTTPS提供。 AppMeasurement無法存取作業階段儲存中的連結追蹤資料，因為通訊協定不同。
* 作業儲存不適用於各個子網域。 例如，訪客導覽至， `store.example.com`然後導覽至 `toys.example.com`。 AppMeasurement無法存取作業儲存中的連結追蹤資料，因為不同的子網域。

> [!TIP] 使用作業儲存區進行連結追蹤的最可靠實作，是透過單一子網域上的HTTPS來支援所有內容。
AppMeasurement會在傳送點擊至Adobe後移除工作階段儲存連結追蹤資料。 當瀏覽器標籤關閉時，它也會自動過期。

## 在Adobe Experience Platform Launch中使用連結追蹤工作階段儲存

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement中的s.useLinkTrackSessionStorage和Launch自訂代碼編輯器

變 `s.useLinkTrackSessionStorage` 數是布林值，可判斷AppMeasurement是否使用作業儲存來追蹤連結資料，而非 `s_sq` Cookie。 Its default value is `false`. 如果您想要AppMeasurement `true` 使用作業儲存，而非Cookie來追蹤連結和Activity map, `s_sq` 請將此變數設為。

```js
s.useLinkTrackSessionStorage = true;
```

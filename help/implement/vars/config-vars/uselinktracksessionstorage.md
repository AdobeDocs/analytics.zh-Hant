---
title: useLinkTrackSessionStorage
description: 將連結追蹤資料存放在工作階段存放區中，而非 Cookie。
feature: Variables
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 81%

---

# useLinkTrackSessionStorage

如果您的組織使用連結追蹤功能，AppMeasurement 會使用 `s_sq` Cookie 傳遞點擊之間的資訊。部分網站設定會與此 Cookie 衝突。如果您想要將瀏覽器工作階段存放區用於連結追蹤和 Activity Map 資料，而非 Cookie，請啟用此變數。

將瀏覽器的工作階段存放區用於連結追蹤有幾項限制：

* 工作階段存放區不會在通訊協定之間運作。例如，您有一個頁面透過 HTTP 提供，而下一個頁面則透過 HTTPS 提供。AppMeasurement 無法存取工作階段存放區中的連結追蹤資料，因為通訊協定不同。
* 工作階段存放區不會在子網域間運作。例如，訪客導覽至 `store.example.com`，然後導覽至 `toys.example.com`。AppMeasurement 無法存取工作階段存放區中的連結追蹤資料，因為子網域不同。

>[!TIP]
>
> 將工作階段存放區用於連結追蹤最可靠的實施，會透過單一子網域上的 HTTPS 提供所有內容。

AppMeasurement 會在傳送點擊至 Adobe 後，移除工作階段存放區連結追蹤資料。關閉瀏覽器標記時，此資料也會自動過期。

## 使用Web SDK使用連結跟蹤會話儲存

Web SDK不支援此功能。

## 使用鏈路跟蹤會話儲存，使用Adobe Analytics擴展

Adobe Analytics擴展中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## s.useLinkTrackSessionStorage在AppMeasurement中和分析擴展自定義代碼編輯器

`s.useLinkTrackSessionStorage` 變數是布林值，可判斷 AppMeasurement 是否將工作階段存放區用於連結追蹤資料，而非 `s_sq` Cookie。其預設值為 `false`。如果您想要 AppMeasurement 將工作階段存放區，而非 `true` Cookie，用於連結追蹤和 Activity Map，請將此變數設為 `s_sq`。

```js
s.useLinkTrackSessionStorage = true;
```

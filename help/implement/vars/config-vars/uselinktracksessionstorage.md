---
title: useLinkTrackSessionStorage
description: 將連結追蹤資料存放在工作階段存放區中，而非 Cookie。
feature: Appmeasurement Implementation
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/JQc7Ii-LrL8k0KIttWFuowJCASGK2e75exSbjhG347s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 86%

---

# useLinkTrackSessionStorage

如果您的組織使用連結追蹤功能，AppMeasurement 會使用 `s_sq` Cookie 傳遞點擊之間的資訊。 部分網站設定會與此 Cookie 衝突。 如果您想要將瀏覽器工作階段存放區用於連結追蹤和 Activity Map 資料，而非 Cookie，請啟用此變數。

將瀏覽器的工作階段存放區用於連結追蹤有幾項限制：

* 工作階段存放區不會在通訊協定之間運作。 例如，您有一個頁面透過 HTTP 提供，而下一個頁面則透過 HTTPS 提供。 AppMeasurement 無法存取工作階段存放區中的連結追蹤資料，因為通訊協定不同。
* 工作階段存放區不會在子網域間運作。 例如，訪客導覽至 `store.example.com`，然後導覽至 `toys.example.com`。 AppMeasurement 無法存取工作階段存放區中的連結追蹤資料，因為子網域不同。

>[!TIP]
>
>將工作階段存放區用於連結追蹤最可靠的實施，會透過單一子網域上的 HTTPS 提供所有內容。

AppMeasurement 會在傳送點擊至 Adobe 後，移除工作階段存放區連結追蹤資料。 關閉瀏覽器標記時，此資料也會自動過期。

## 透過Web SDK使用連結追蹤工作階段存放區

網頁SDK不支援此功能。

## 透過Adobe Analytics擴充功能使用連結追蹤工作階段存放區

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.useLinkTrackSessionStorage

`s.useLinkTrackSessionStorage` 變數是布林值，可判斷 AppMeasurement 是否將工作階段存放區用於連結追蹤資料，而非 `s_sq` Cookie。 其預設值為 `false`。 如果您想要 AppMeasurement 將工作階段存放區，而非 `true` Cookie，用於連結追蹤和 Activity Map，請將此變數設為 `s_sq`。

```js
s.useLinkTrackSessionStorage = true;
```

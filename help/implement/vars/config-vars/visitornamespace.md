---
title: visitorNameSpace
description: （已淘汰）協助判斷第三方Cookie網域。
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/y9oXzSzgN-s8gVrdHs0nFRm0ASSbUPzlkW-V6u1GnMg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 89%

---

# visitorNamespace

>[!IMPORTANT]
>
>此變數已淘汰。 請改用 [`trackingServer`](trackingserver.md)。

在舊版 Adobe Analytics 中，AppMeasurement 使用 `visitorNameSpace` 變數來協助判斷儲存訪客 Cookie 的 `2o7.net` 子網域。 近代瀏覽器中逐漸增強的隱私權實務會降低第三方 Cookie 的可靠性。 隨著 `trackingServer` 和 [`trackingServerSecure`](trackingserversecure.md) 變數的引入，您不再需要 `visitorNameSpace`。

>[!TIP]
>
>Adobe 建議您在網站上使用第一方 Cookie。 第一方 Cookie 不使用此變數。

## 使用Adobe Analytics擴充功能的訪客名稱空間

「[!UICONTROL 訪客命名空間]」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL Cookie]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「Cookie」]摺疊式功能表，如此可顯示[!UICONTROL 「訪客命名空間」]欄位。

Adobe 建議您不要使用此欄位。 請改用 `trackingServer` 和 `trackingServerSecure`。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.visitorNamespace

`s.visitorNamespace` 變數是字串，其中包含每個組織特有的獨特值。 從舊版 Adobe Analytics 下載舊版 AppMeasurement 資料庫時，此獨特值會自動包含在內。 除非 `trackingServer` 和 `trackingServerSecure` 未設定，否則目前的 AppMeasurement 資料庫不會使用此變數。

如果貴組織仍需要此變數，請挑選能代表貴組織的值。 您可以將此值儲存在[解決方案設計文件](../../prepare/solution-design.md)中。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```

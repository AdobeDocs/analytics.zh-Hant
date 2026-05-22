---
title: Util.cookieRead
description: 取得 Cookie 的值。
feature: Appmeasurement Implementation
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/puEimpy5b-hdgo186YqHzsgxC-LGKPluxN5mVdxFer4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 72%

---

# Util.cookieRead

Cookie可以儲存和擷取相同網域上各頁面的資訊。 使用 `Util.cookieRead()` 方法可從 Cookie 擷取值。

## 使用Adobe Analytics擴充功能和Web SDK擴充功能來讀取Cookie

您可以透過在資料元素中設定值來讀取 Cookie。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 資料元素]標記，然後按一下所需的資料元素 (或建立資料元素)。
4. 將[!UICONTROL 擴充功能]下拉式清單設定為&#x200B;**[!UICONTROL 核心]**，並將[!UICONTROL 資料元素型別]設定為&#x200B;**[!UICONTROL Cookie]**。
5. 在文字欄位中輸入 Cookie 名稱。

Cookie 值會儲存在資料元素中。 接著，您可以參考規則中的資料元素，以指派所需的變數。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.Util.cookieRead()

呼叫 `s.Util.cookieRead()` 方法以讀取所需的 Cookie 值。 其唯一引數是必要的字串。 此方法會傳回包含 Cookie 值的字串。 如果 Cookie 不存在，則會傳回空字串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```

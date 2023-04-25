---
title: Util.cookieRead
description: 取得 Cookie 的值。
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 72%

---

# Util.cookieRead

Cookie可以儲存和擷取相同網域上各頁面的資訊。使用 `Util.cookieRead()` 方法可從 Cookie 擷取值。

## 使用Adobe Analytics擴充功能和Web SDK擴充功能讀取Cookie

您可以透過在資料元素中設定值來讀取 Cookie。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 資料元素]標記，然後按一下所需的資料元素 (或建立資料元素)。
4. 設定 [!UICONTROL 擴充功能] 下拉清單至 **[!UICONTROL 核心]**，和 [!UICONTROL 資料元素類型] to **[!UICONTROL Cookie]**.
5. 在文字欄位中輸入 Cookie 名稱。

Cookie 值會儲存在資料元素中。然後，您就可以參考規則中的資料元素，以指派所需的變數。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.Util.cookieRead()

呼叫 `s.Util.cookieRead()` 方法以讀取所需的 Cookie 值。其唯一引數是必要的字串。此方法會傳回包含 Cookie 值的字串。如果 Cookie 不存在，則會傳回空字串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```

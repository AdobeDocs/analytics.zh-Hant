---
title: Util.cookieRead
description: 取得 Cookie 的值。
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '171'
ht-degree: 100%

---

# Util.cookieRead

Cookie可以儲存和擷取相同網域上各頁面的資訊。使用 `Util.cookieRead()` 方法可從 Cookie 擷取值。

## 使用 Adobe Experience Platform 中的標記讀取 Cookie

您可以透過在資料元素中設定值來讀取 Cookie。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 資料元素]標記，然後按一下所需的資料元素 (或建立資料元素)。
4. 將 [!UICONTROL 「擴充功能」]下拉式清單設定為[!UICONTROL 「核心」]，並將[!UICONTROL 「資料元素類型」]設定為[!UICONTROL 「Cookie」]。
5. 在文字欄位中輸入 Cookie 名稱。

Cookie 值會儲存在資料元素中。接著，您可以參考規則中的資料元素來指派 Analytics 變數。

## AppMeasurement 和自訂程式碼編輯器中的 s.Util.cookieRead()

呼叫 `s.Util.cookieRead()` 方法以讀取所需的 Cookie 值。其唯一引數是必要的字串。此方法會傳回包含 Cookie 值的字串。如果 Cookie 不存在，則會傳回空字串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```

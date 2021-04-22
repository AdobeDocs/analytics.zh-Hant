---
title: Util.cookieRead
description: 取得 Cookie 的值。
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '167'
ht-degree: 100%

---

# Util.cookieRead

Cookie可以儲存和擷取相同網域上各頁面的資訊。使用 `Util.cookieRead()` 方法可從 Cookie 擷取值。

## 在 Adobe Experience Platform Launch 中讀取 Cookie

您可以透過在資料元素中設定值來讀取 Cookie。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 資料元素]標籤，然後按一下所需的資料元素 (或建立資料元素)。
4. 將 [!UICONTROL 「擴充功能」]下拉式清單設定為[!UICONTROL 「核心」]，並將[!UICONTROL 「資料元素類型」]設定為[!UICONTROL 「Cookie」]。
5. 在文字欄位中輸入 Cookie 名稱。

Cookie 值會儲存在資料元素中。接著，您可以參考規則中的資料元素來指派 Analytics 變數。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.Util.cookieRead()

呼叫 `s.Util.cookieRead()` 方法以讀取所需的 Cookie 值。其唯一引數是必要的字串。此方法會傳回包含 Cookie 值的字串。如果 Cookie 不存在，則會傳回空字串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```

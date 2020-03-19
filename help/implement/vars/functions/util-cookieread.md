---
title: Util.cookieRead
description: 取得 Cookie 的值。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Util.cookieRead

Cookie可以儲存和擷取相同網域上各頁面的資訊。 使用 `Util.cookieRead()` 方法從Cookie擷取值。

## 閱讀Adobe Experience Platform Launch中的Cookie

您可以透過在資料元素中設定值來讀取Cookie。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Data Elements] ，然後按一下所需的資料元素（或建立資料元素）。
4. 將下拉 [!UICONTROL Extension] 式清單設 [!UICONTROL Core]定為，並 [!UICONTROL Data Element Type] 將設為 [!UICONTROL Cookie]。
5. 在文字欄位中輸入Cookie名稱。

Cookie值會儲存在資料元素中。 然後，您可以參考規則中的資料元素來指派Analytics變數。

## AppMeasurement和Launch自訂代碼編輯器中的s.Util.cookieRead()

呼叫方 `s.Util.cookieRead()` 法以讀取所需的Cookie值。 其唯一引數是字串，此為必要項。 此方法會傳回包含Cookie值的字串。 如果Cookie不存在，則會傳回空字串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```

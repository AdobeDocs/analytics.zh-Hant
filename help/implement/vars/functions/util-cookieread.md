---
title: Util.cookieRead
description: 取得 Cookie 的值。
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 73%

---

# Util.cookieRead

Cookie可以儲存和擷取相同網域上各頁面的資訊。使用 `Util.cookieRead()` 方法可從 Cookie 擷取值。

## 使用Adobe Analytics擴展和Web SDK擴展讀取Cookie

您可以透過在資料元素中設定值來讀取 Cookie。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 資料元素]標記，然後按一下所需的資料元素 (或建立資料元素)。
4. 將 [!UICONTROL 「擴充功能」]下拉式清單設定為&#x200B;**[!UICONTROL 「核心」]**，並將[!UICONTROL 「資料元素類型」]設定為&#x200B;**[!UICONTROL 「Cookie」]**。
5. 在文字欄位中輸入 Cookie 名稱。

Cookie 值會儲存在資料元素中。然後，可以引用規則中的資料元素來指定所需的變數。

## AppMeasurement中的s.Util.cookieRead()和Analytics擴展自定義代碼編輯器

呼叫 `s.Util.cookieRead()` 方法以讀取所需的 Cookie 值。其唯一引數是必要的字串。此方法會傳回包含 Cookie 值的字串。如果 Cookie 不存在，則會傳回空字串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```

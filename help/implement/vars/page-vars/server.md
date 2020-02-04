---
title: server
description: 填入「伺服器」維度。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# server

變數 `server` 通常會儲存您網站的主機名稱。 它常用於包含多個網域資料的報表套裝。 它的功能與prop相同。

## Adobe Experience Platform Launch中的伺服器

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定伺服器。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到「 [!UICONTROL Server] （伺服器）」部分。

您可以將伺服器設定為任何字串值或資料元素。

## AppMeasurement和Launch自訂代碼編輯器中的s.server

變 `s.server` 數是一個字串，通常包含您網站的主機名稱。 其最大值為100個位元組；較長的值會被截斷。

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

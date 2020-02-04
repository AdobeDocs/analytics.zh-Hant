---
title: pageName
description: 您網站上的頁面名稱。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# pageName

變 `pageName` 數通常會儲存指定頁面的名稱。 確定哪些頁面最受歡迎是很有幫助的。 此變數會填入「頁面名稱」維度。

> [!NOTE] 此維度一律會從連結追蹤呼叫中移除。 如果您想查看追蹤連結的頁面名稱，請考慮將此變數複製至eVar。

如果此變數未定義於指定的頁面追蹤呼叫，則會改 `pageURL` 用變數。

## Adobe Experience Platform Launch中的頁面名稱

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定頁面名稱。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到「頁 [!UICONTROL 面名稱] 」區段。

您可以將頁面名稱設為任何字串值，包括資料元素。

## AppMeasurement和Launch自訂代碼編輯器中的s.pageName

變 `s.pageName` 數是通常包含頁面名稱的字串。 其最大值為100個位元組；較長的值會被截斷。 此截斷包含例項，若此變數為空 `pageURL` 白，則會回溯至該例項。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

---
title: pageName
description: 網站上各個頁面的名稱。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '226'
ht-degree: 100%

---


# pageName

`pageName` 變數通常會儲存指定頁面的名稱。這個變數有助於判斷哪些個別頁面最受歡迎。此變數會填入「頁面名稱」維度。

>[!NOTE]
>
>此維度一律會從連結追蹤呼叫中移除。如果您想查看追蹤連結的頁面名稱，請考慮將此變數複製到 eVar。

如果您未在指定頁面追蹤呼叫上設定此變數，系統會改用 [`pageURL`](pageurl.md) 變數。

## Adobe Experience Platform Launch 中的頁面名稱

您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面名稱，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「頁面名稱」]區段。

您可以將頁面名稱設為任何字串值，包括資料元素。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.pageName

`s.pageName` 變數是字串，通常包含頁面的名稱。其最大值為 100 個位元組；超過上限的值會遭到截斷。此處的截斷包含當此變數為空白時回溯為 `pageURL` 的情況。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

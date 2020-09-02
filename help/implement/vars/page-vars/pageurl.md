---
title: pageURL
description: 覆寫在網站上自動收集的頁面 URL。
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 81%

---


# pageURL

AppMeasurement 會自動收集每次點擊中的頁面 URL。如果您想要覆寫 AppMeasurement 自動收集的頁面 URL，可以使用此變數。在大多數情況下，您不需要設定此變數。

>[!NOTE]
>
>此變數不是 Analysis Workspace 中的可用維度。它僅適用於 Data Warehouse 和資料摘要。此外，Adobe資料收集伺服器會從所有連結追蹤影像要求中 [移除此](/help/implement/vars/functions/tl-method.md) 維度。 如果您想要在「分析工作區」中將頁面URL當做維度，或想在連結追蹤點擊中使用此維度，請考慮在每次點擊 `pageURL` 時將變數 [傳入eVar](evar.md) 。

## Adobe Experience Platform Launch 中的頁面 URL

Launch 會自動填入頁面 URL。不過，您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面 URL 覆寫，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往&#x200B;**[!UICONTROL 規則]**&#x200B;標籤，然後按一下所需的規則 (或建立規則)。
4. 在&#x200B;**[!UICONTROL 「動作」]**&#x200B;下方按一下現有的&#x200B;**[!UICONTROL 「Adobe Analytics - 設定變數」]**&#x200B;動作，或按一下「+」圖示。
5. 將&#x200B;**[!UICONTROL 「擴充功能」]**&#x200B;下拉式清單設為「Adobe Analytics」，再將&#x200B;**[!UICONTROL 「動作類型」]**&#x200B;設為&#x200B;**[!UICONTROL 「設定變數」]**。
6. 找出&#x200B;**[!UICONTROL 「頁面 URL」]**&#x200B;區段。

您可以將頁面 URL 設為任何字串值。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.pageURL

`s.pageURL` 變數是包含頁面 URL 的字串。AppMeasurement 會自動收集此變數，不過您可以視需要覆寫其值。

```js
s.pageURL = "https://example.com";
```

如果您想要將頁面 URL 當做報表中的維度，請考慮在實施中使用下列項目：

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```

如果使用數 `digitalData` 據 [層](../../prepare/data-layer.md):

```js
s.pageURL = digitalData.page.pageInfo.destinationURL;
```

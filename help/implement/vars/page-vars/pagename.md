---
title: pageName
description: 網站上各個頁面的名稱。
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 81%

---

# pageName

`pageName` 變數通常會儲存指定頁面的名稱。這個變數有助於判斷哪些個別頁面最受歡迎。此變數會填入「[頁面](/help/components/dimensions/page.md)」維度。

如果您未在指定頁面追蹤呼叫上設定此變數，系統會改用 [`pageURL`](pageurl.md) 變數。

>[!NOTE]
>
>Adobe 資料收集伺服器會從所有 [連結追蹤](/help/implement/vars/functions/tl-method.md) 影像要求中移除此維度。如果您想要此點擊出現在連結追蹤點擊中，請考慮將維度複製到 [eVar](evar.md)。

## 使用Web SDK的頁面名稱

頁面是 [已對應至Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM欄位下 `web.webPageDetails.name`.

## 使用Adobe Analytics擴充功能的頁面名稱

您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面名稱，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 設定 [!UICONTROL 擴充功能] 下拉式清單至Adobe Analytics，以及 [!UICONTROL 動作類型] to [!UICONTROL 設定變數].
6. 找出[!UICONTROL 「頁面名稱」]區段。

您可以將頁面名稱設為任何字串值，包括資料元素。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.pageName

`s.pageName` 變數是字串，通常包含頁面的名稱。其最大值為 100 個位元組；超過上限的值會遭到截斷。此處的截斷包含當此變數為空白時回溯為 `pageURL` 的情況。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md)：

```js
s.pageName = digitalData.page.pageInfo.pageName;
```

---
title: pageName
description: 網站上各個頁面的名稱。
feature: Variables
exl-id: 24ac40a9-f0e7-4534-abf2-2397f5fe16c2
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 80%

---

# 頁名

`pageName` 變數通常會儲存指定頁面的名稱。這個變數有助於判斷哪些個別頁面最受歡迎。此變數會填入「[頁面](/help/components/dimensions/page.md)」維度。

如果您未在指定頁面追蹤呼叫上設定此變數，系統會改用 [`pageURL`](pageurl.md) 變數。

>[!NOTE]
>
>Adobe 資料收集伺服器會從所有 [連結追蹤](/help/implement/vars/functions/tl-method.md) 影像要求中移除此維度。如果您想要此點擊出現在連結追蹤點擊中，請考慮將維度複製到 [eVar](evar.md)。

## 使用Web SDK的頁名

頁面是 [映射為Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM欄位下 `web.webPageDetails.name`。

## 使用Adobe Analytics副檔名的頁名

您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面名稱，或依據規則進行設定。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 規則]標記，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「頁面名稱」]區段。

您可以將頁面名稱設為任何字串值，包括資料元素。

## AppMeasurement中的s.pageName和Analytics擴展自定義代碼編輯器

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

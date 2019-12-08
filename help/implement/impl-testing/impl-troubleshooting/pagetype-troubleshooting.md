---
description: pageType 變數的用途僅止於指定 404 (找不到頁面) 錯誤頁面。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 正確設定 PageType 變數
topic: Developer and implementation
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 正確設定 PageType 變數

pageType 變數的用途僅止於指定 404 (找不到頁面) 錯誤頁面。

此變數只有一個可能的值，即 errorPage。

```js
pageType="errorPage"
```

在 404 錯誤頁面上，*`pageName`*&#x200B;變數不應填入。*`pageType`* 變數只能在指定的 404 錯誤頁面上設定。任何包含內容的頁面，在 *`pageType`* 變數中都絕不應該有值。對於包含內容的頁面，您可以透過下列方式設定此變數: 

```js
pageType=""
```

建議您應從包含內容的頁面中完全刪除此變數。此建議作法是為了避免變數用途方面的混淆。

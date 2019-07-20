---
description: pageType 變數的用途僅止於指定 404 (找不到頁面) 錯誤頁面。
keywords: Analytics 實施
seo-description: pageType 變數的用途僅止於指定 404 (找不到頁面) 錯誤頁面。
seo-title: 正確設定pageType變數
solution: Analytics
subtopic: 疑難排解
title: 正確設定pageType變數
topic: 開發人員和實施
uuid: eafafa58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 正確設定pageType變數

pageType 變數的用途僅止於指定 404 (找不到頁面) 錯誤頁面。

此變數只有一個可能的值，即 errorPage。

```js
pageType="errorPage"
```

在 404 錯誤頁面上，*`pageName`*&#x200B;變數不應填入。*`pageType`* 變數只能在指定的404錯誤頁面上設定。Any page containing content should never have a value in the *`pageType`* variable. 對於包含內容的頁面，您可以透過下列方式設定此變數: 

```js
pageType=""
```

建議您應從包含內容的頁面中完全刪除此變數。此建議作法是為了避免變數用途方面的混淆。

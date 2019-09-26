---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.usePlugins

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

## 語法和可能的值

```js
s.usePlugins=true|false
```

[!UICONTROL usePlugins] 變數應為 'true' 或 'false'。

## 範例

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

[!UICONTROL usePlugins] 變數在  *`s_doPlugins`* function is not declared in your JavaScript file.

## 組態設定

無
---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.usePlugins

若此函數可供使用且包含有用的程式碼，則 [!UICONTROL s_usePlugins] 應設為「true」。

當 [!UICONTROL usePlugins] 設為「true」時，則會在每個影像要求之前呼叫 *`s_doPlugins`* 函數。

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

若未在 JavaScript 檔案中宣告 *`s_doPlugins`* 函數，[!UICONTROL usePlugins] 變數僅應為 false (或未宣告)。

## 組態設定

無

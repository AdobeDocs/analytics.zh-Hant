---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.doPlugins

 變數是 函數的參考，可讓 函數在 JavaScript 檔案內的適當位置被呼叫。

The *`s_doPlugins`* function is called each time any of the following occurs:

* The  function is called *`t()`*
* 函 *`tl()`* 數稱為
* 點按退出或下載連結
* 點按訪客點按對映所追蹤的任何頁面元素

 此&#x200B;*`doPlugins`* 函數可用來執行自訂常式，以蒐集或變更資料。If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the  function should be called s_mc_doPlugins.*`s_doPlugins`*

## 語法和可能的值

函 *`s_doPlugins`* 數不應以引號括起來， *`doPlugins`* 且應始終指派給函式的確切名稱( *`s_doPlugins`* 如果該函式已重新命名)。

```js
s.doPlugins=s_doPlugins;
```

## 範例

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## 組態設定

無

## 缺陷、問題和提示

* 您將內容與其他客戶共用，或提取其他客戶的內容，是唯一須變更物件名稱 (例如從 s 變更為 s_mc) 的原因。重新命名  *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* 如果您意外地開始從其他Adobe客戶提取內容，而您的 *`s_doPlugins`* 函式正被覆寫，則可以直接重新命名函式，而不變更 *`s_doPlugins`* 物件名稱。 雖然最理想的解決方案是使用與相同頁面上的其他 JavaScript 檔案不同的物件名稱，但這並非必要動作。
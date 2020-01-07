---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---



# s.doPlugins

 變數是 函數的參考，可讓 函數在 JavaScript 檔案內的適當位置被呼叫。

每當發生下列任一情況時，則會呼叫 *`s_doPlugins`* 函數:

* 呼叫 *`t()`* 函數
* 呼叫 *`tl()`* 函數
* 點按退出或下載連結
* 點按訪客點按對映所追蹤的任何頁面元素

 此&#x200B;*`doPlugins`* 函數可用來執行自訂常式，以蒐集或變更資料。如果您使用「s」以外的物件名稱，請務必適當地重新命名 *`s_doPlugins`*。例如，如果物件名稱為 s_mc，*`s_doPlugins`* 函數則應稱為 s_mc_doPlugins。

## 語法和可能的值

不應以引號括住 *`s_doPlugins`* 函數，且 *`doPlugins`* 應一律指派給 *`s_doPlugins`* 函數的確切名稱 (在該函數已重新命名的情況下)。

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

* 您將內容與其他客戶共用，或提取其他客戶的內容，是唯一須變更物件名稱 (例如從 s 變更為 s_mc) 的原因。重新命名  *`s_doPlugins`* 函數為 [!UICONTROL s_mc_doPlugins]，可確保其他客戶的 JavaScript 檔案不會覆寫您的 *`doPlugins`* 函數。

* 如果您意外地從其他 Adobe 客戶開始提取內容，而 *`s_doPlugins`* 函數正遭到覆寫，您可以直接重新命名 *`s_doPlugins`* 函數，而不變更物件名稱。雖然最理想的解決方案是使用與相同頁面上的其他 JavaScript 檔案不同的物件名稱，但這並非必要動作。

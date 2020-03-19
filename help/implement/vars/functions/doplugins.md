---
title: doPlugins
description: 在編譯點擊並傳送至Adobe之前設定邏輯。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# doPlugins

變 `doPlugins` 數會當成「最後呼叫」，用來設定實作中的值。 如果 [`usePlugins`](../config-vars/useplugins.md) 已啟用，則會在編譯任何類型的影像要求並傳送至Adobe之前自動執行，包括：

* 所有頁面檢視([`t()`](t-method.md))呼叫
* 所有連結追蹤([`tl()`](tl-method.md))呼叫，包括自動下載連結和退出連結

使用 `doPlugins` 變數來呼叫外掛程式程式碼，並在編譯影像要求並傳送至Adobe之前設定最終變數值。

## Adobe Experience Platform Launch的增效模組

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement中的s.doPlugins和Launch自訂代碼

將變數 `s.doPlugins` 設為包含所需程式碼的函式。 當您進行追蹤呼叫時，函式會自動執行。

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] 在實作中，只將函 `doPlugins` 數設定為變數一次。 如果您設定 `doPlugins` 變數多次，則只會使用最新的程式碼。

## 範例

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

> [!NOTE] 舊版AppMeasurement的程式碼稍有 `doPlugins()` 不同。 Adobe建議您使用上述格式作為最佳實務。

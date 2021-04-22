---
title: doPlugins
description: 在編譯點擊並傳送至 Adobe 之前設定邏輯。
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '182'
ht-degree: 100%

---

# doPlugins

`doPlugins` 變數會成為「最後呼叫」，負責設定實施中的值。如果啟用 [`usePlugins`](../config-vars/useplugins.md)，它會在任何類型的影像要求編譯並傳送至 Adobe 之前自動執行，包括：

* 所有頁面檢視 ([`t()`](t-method.md)) 呼叫
* 所有連結追蹤 ([`tl()`](tl-method.md)) 呼叫，包括自動下載連結和退出連結

使用 `doPlugins` 變數來呼叫外掛程式程式碼，並在影像要求編譯並傳送至 Adobe 之前設定最終變數值。

## Adobe Experience Platform Launch 中的外掛程式

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼中的 s.doPlugins

將變數 `s.doPlugins` 設為包含所需程式碼的函數。當您進行追蹤呼叫時，函數會自動執行。

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
> 實施作業中的 `doPlugins` 函數只需要設為變數一次。如果您設定 `doPlugins` 變數多次，只需要使用最新的程式碼就可以了。

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

>[!NOTE]
>
>舊版 AppMeasurement 的 `doPlugins()` 程式碼稍有不同。Adobe 建議您使用上述格式作為最佳實務。

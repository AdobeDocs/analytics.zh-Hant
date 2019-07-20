---
description: JavaScript 適用的 AppMeasurement 是新的程式庫，提供與 s_code.js 相同的核心功能，但可更加輕巧快速地在行動與桌面網站上使用。
keywords: appmeasurement；Analytics實作；javascript；javascript的appMeasurement；初始化；擷取AppMeasurement例項；clear vars；clearvars；appmeasurement公用程式；appmeasurement instance；AppMeasurement優點
seo-description: JavaScript 適用的 AppMeasurement 是新的程式庫，提供與 s_code.js 相同的核心功能，但可更加輕巧快速地在行動與桌面網站上使用。
seo-title: 關於 JavaScript 適用的 AppMeasurement
solution: Analytics
subtopic: JavaScript AppMeasurement
title: 關於 JavaScript 適用的 AppMeasurement
topic: 開發人員和實施
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 關於 JavaScript 適用的 AppMeasurement

[!DNL AppMeasurement]JavaScript 適用的 是新的程式庫，提供與 s_code.js 相同的核心功能，但可更加輕巧快速地在行動與桌面網站上使用。

## 移轉前須知 {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* 有些外掛程式已不受支援。See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* The library does not support dynamic account selection ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* The library and page code can be deployed inside the `<head>` tag.
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. 「調查」模組不受支援。
* 您現有的頁面程式碼與新版本相容。
* 程式庫提供原生公用程式，用以取得查詢參數、讀取和寫入 Cookie，以及執行進階連結追蹤。

## 常問的問題 {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## 初始化過程 {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

`s_gi` 呼叫時，如果指定 [!DNL AppMeasurement]`s_account`的例項不存在，則會建立新例項。否則傳回現有例項。如此可避免為相同的帳戶建立重複物件。

## 擷取 AppMeasurement 例項 {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## 公用程式 {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## 清除變數 {#section_597C411E7EDB42BC9A6A0508C9D57147}

有新的 `clearVars` 方法可用來清除下列例項物件中的值: 

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

例如:

```js
s.clearVars()
```

## 福利 {#section_091E5A28E89E438E8A54A95F55165743}

* 較 H.25 代碼快 3-7 倍。
* 未壓縮大小僅為 21k，而採用 gzipped 壓縮的大小為 8k (H.25 代碼的未壓縮大小為 33k，而採用 gzipped 的大小為 13 k)。
* 數個常用外掛程式 () 的原生支援。
* 輕便快速且功能強大，無論在行動版網頁或桌面完整版網頁皆可輕鬆使用，可讓您在所有的網站環境中使用單一程式庫。


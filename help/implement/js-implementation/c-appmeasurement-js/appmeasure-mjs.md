---
description: JavaScript 適用的 AppMeasurement 是新的程式庫，提供與 s_code.js 相同的核心功能，但可更加輕巧快速地在行動與桌面網站上使用。
keywords: appmeasurement;Analytics Implementation;javascript;appmeasurement for javascript;initialization;retrieve appmeasurement instance;clear vars;clearvars;appmeasurement utilities;appmeasurement instance;appmeasurement benefits
subtopic: JavaScript AppMeasurement
title: 關於 JavaScript 適用的 AppMeasurement
topic: Developer and implementation
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 關於 JavaScript 適用的 AppMeasurement

[!DNL AppMeasurement]JavaScript 適用的 是新的程式庫，提供與 s_code.js 相同的核心功能，但可更加輕巧快速地在行動與桌面網站上使用。

## 移轉前須知 {#section_B8E7B39E8469468883BA0B41234F21C4}

下列清單包含您在切換為此新版 [!DNL AppMeasurement] 之前所需瞭解的變更:

* 有些外掛程式已不受支援。詳情請參閱 [AppMeasurement 外掛程式支援](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md)。
* 此程式庫不支援動態帳戶選項 ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md)、[dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md) 和 [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md))。

* 程式庫和頁面程式碼可部署在 `<head>` 標籤中。
* 媒體和整合模組可使用 JavaScript [!DNL AppMeasurement] 下載套件中的更新模組代碼來支援。「調查」模組不受支援。
* 您現有的頁面程式碼與新版本相容。
* 程式庫提供原生公用程式，用以取得查詢參數、讀取和寫入 Cookie，以及執行進階連結追蹤。

## 常見問題集 {#section_9BD41B08F7B54197B230937714B9357A}

如需效能、視訊追蹤、行動等相關資訊，請參閱[常見問題集](/help/implement/faq.md)。

## 初始化過程 {#section_F6D5680F6D134B6AB1F01C6235860635}

呼叫 `s_gi()`，傳遞報表套裝 ID 以初始化 [!DNL AppMeasurement] 例項:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

當呼叫 `s_gi` 時，如果指定的 `s_account` 不存在 [!DNL AppMeasurement] 例項，則會建立新例項。否則傳回現有例項。如此可避免為相同的帳戶建立重複物件。

## 擷取 AppMeasurement 例項 {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

在整個程式碼中，呼叫全域 [s_gi() 函數](/help/implement/js-implementation/function-s-gi.md)以擷取現有 [!DNL AppMeasurement] 例項。

## 公用程式 {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] 提供下列內建公用程式:

* [Util.cookieRead](/help/implement/js-implementation/util-cookieread.md)
* [Util.cookieWrite](/help/implement/js-implementation/util-cookiewrite.md)
* [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md)

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


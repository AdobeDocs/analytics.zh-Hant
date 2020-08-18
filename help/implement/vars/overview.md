---
title: 變數、函數、方法和外掛程式概述
description: 瞭解您可在傳送至 Adobe 的資料中加入哪些變數，進而改善報表。
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 97%

---


# 變數、函數、方法和外掛程式概述

Analytics 提供數個變數，可用於收集 Analytics 資料。本節中的變數分為幾個部分：

* **頁面變數**&#x200B;通常是直接用於報表中的值。常見的頁面變數包括 `props`、`eVars` 和 `events`。
* **設定變數**&#x200B;是有助於確保將正確資料送達 Adobe 的設定值。常見的設定變數包括 `trackingServerSecure`、`charSet` 和 `linkTrackVars`。設定變數通常不會填入維度項目。
* **函數和方法**&#x200B;是參考時執行特定工作的程式碼片段。常見的函數包括 `t()`、`tl()` 和 `clearVars()`。

## 變數與實施方法

Adobe 提供多種實施 Adobe Analytics 的方式。每個頁面都提供一個小節，說明如何使用 Launch 和 JavaScript 適用的 AppMeasurement 實施變數。

## 操作順序

Adobe Analytics 發佈的 AppMeasurement 資料庫在傳送資料至 Adobe 時，會遵循特定順序。如果您未按照順序執行這些任務，資料可能會不完整。

1. 若您的網站使用資料層，請先確認所有適用的變數均會填入。如需詳細資訊，請參閱[資料層](../prepare/data-layer.md)。
2. 使用資料層填入 Analytics 變數。如果您使用 Launch，只要使用資料元素，然後將資料元素指派給變數，就能輕鬆完成這項工作。請參 Launch 使用指南中的[資料元素](https://docs.adobe.com/content/help/zh-Hant/launch/using/reference/manage-resources/data-elements.html)。
3. 呼叫追蹤函數。大部分的 AppMeasurement 資料庫都使用 `t()` 方法，不過有些行動 SDK 使用 `track()`。呼叫追蹤函數時，Analytics 物件中定義的所有支援變數，都會以影像要求的形式傳送至 Adobe。

## 非法字元

JavaScript 變數不允許使用下列字元和字串。

* 定位 (`0x09`)
* 歸位 (`0x0D`)
* 新行 (`0x0A`)
* HTML 標籤 (例如 `<b></b>` 或 `&#153`)

有些變數有其他限制或語法要求。例如，[`products`](page-vars/products.md) 變數會保留分號和逗號來分隔不同的產品和類別。

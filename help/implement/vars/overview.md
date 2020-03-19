---
title: 變數、函式、方法和外掛程式概觀
description: 瞭解您可在傳送至Adobe的資料中加入哪些變數，以改善報表。
keywords: appmeasurement,variables,vars,configuration,page,implementation
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# 變數、函式、方法和外掛程式概觀

Analytics 提供數個變數，可用於收集 Analytics 資料。此區段中的變數會分割為數個區段：

* **頁面變數** ，是通常直接用於報表的值。 常見的頁面變 `props`數包括 `eVars`、和 `events`。
* **設定變數** ，是可協助確保正確資料送達Adobe的設定值。 常見的組態變 `trackingServerSecure`數包括 `charSet`、和 `linkTrackVars`。 設定變數通常不會填入維度值。
* **函式和方法** ，是參考時執行特定工作的程式碼片段。 常見功能 `t()`包括 `tl()`、和 `clearVars()`。

## 變數與實作方法

Adobe提供多種實作Adobe Analytics的方式。 每個頁面都提供一個章節，說明如何使用Launch和AppMeasurement for JavaScript實作變數。

## 操作順序

Adobe Analytics發佈的AppMeasurement程式庫會在傳送資料至Adobe時遵循特定順序。 如果您不按順序執行這些任務，則資料可能不完整。

1. 若您的網站使用資料層，請確定所有適用的變數都會先填入。 See [Data layer](../prepare/data-layer.md) for more information.
2. 使用資料層填入Analytics變數。 如果您使用Launch，則可使用資料元素，然後將資料元素指派給變數，輕鬆完成這項工作。 See [Data elements](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html) in the Launch user guide.
3. 呼叫追蹤函式。 大部分的AppMeasurement程式庫都 `t()` 會使用此方法，但有些行動SDK會使用 `track()`。 呼叫追蹤函式時，Analytics物件中定義的所有支援變數都會以影像要求的形式傳送至Adobe。

## 非法字元

JavaScript變數不允許使用下列字元和字串。

* 定位 (`0x09`)
* 歸位(`0x0D`)
* 新行 (`0x0A`)
* HTML 標籤 (例如 `<b></b>` 或 `&#153`)

有些變數有其他限制或語法要求。 例如，變數會 `products` 保留分號和逗號來分隔不同的產品和類別。

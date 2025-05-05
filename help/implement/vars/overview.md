---
title: 變數、函數、方法和外掛程式總覽
description: 瞭解您可在傳送至 Adobe 的資料中加入哪些變數，進而改善報表。
keywords: appmeasurement, 變數, vars, 設定, 頁面, 實作
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
role: Admin, Developer
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 67%

---

# 變數、函數、方法和外掛程式總覽

Analytics 提供數個變數，可用於收集 Analytics 資料。本節中的變數分為幾個部分：

* **頁面變數**&#x200B;通常是直接用於報表中的值。常見的頁面變數包括 `props`、`eVars` 和 `events`。
* **設定變數**&#x200B;是有助於確保將正確資料送達 Adobe 的設定值。常見的設定變數包括 `trackingServerSecure`、`charSet` 和 `linkTrackVars`。設定變數通常不會填入維度項目。
* **函數和方法**&#x200B;是參考時執行特定工作的程式碼片段。常見的函數包括 `t()`、`tl()` 和 `clearVars()`。

## 變數與實作方法

Adobe 提供多種實施 Adobe Analytics 的方式。每個頁面都會提供如何使用Web SDK、使用Adobe Analytics擴充功能和JavaScriptAppMeasurement來實作變數的區段。


>[!BEGINSHADEBOX]

請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [設定變數](https://video.tv.adobe.com/v/3456978?quality=12&learn=on&captions=chi_hant){target="_blank"}以取得示範影片。

>[!ENDSHADEBOX]


## 操作順序

Adobe Analytics 發佈的 AppMeasurement 資料庫在傳送資料至 Adobe 時，會遵循特定順序。如果您未按照順序執行這些任務，資料可能會不完整。

1. 若您的網站使用資料層，請先確認所有適用的變數均會填入。例如，您以頁面標題填入`adobeDataLayer.page.title`。 如需詳細資訊，請參閱[資料層](../prepare/data-layer.md)。
2. 使用資料層填入 Analytics 變數。<br/>如果您使用Adobe Experience Platform中的標籤，這項工作會透過在兩者之間使用資料元素來完成。 資料元素會填入資料層的值。 例如，資料元素`Page Title`從資料層變數`adobeDataLayer.page.title`取得值。 <br/>然後您可以使用資料元素來填入Analytics變數。 例如，`eVar4`從資料元素`Page Title`取得值。 <br/>如需詳細資訊，請參閱[資料元素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=zh-Hant)、[將資料層物件對應至資料元素](../launch/layer-to-elements.md)以及[將標籤資料元素對應至Analytics變數](../launch/elements-to-variable.md)
3. 最後，呼叫追蹤函式。 大部分的 AppMeasurement 資料庫都使用 `t()` 方法，不過有些行動 SDK 使用 `track()`。呼叫追蹤函數時，Analytics 物件中定義的所有支援變數，都會以影像要求的形式傳送至 Adobe。

## 非法字元

JavaScript 變數不允許使用下列字元和字串。

* 定位 (`0x09`)
* 歸位 (`0x0D`)
* 新行 (`0x0A`)
* HTML 標記 (例如 `<b></b>` 或 `&#153`)

有些變數有其他限制或語法要求。例如，[`products`](page-vars/products.md) 變數會保留分號和逗號來分隔不同的產品和類別。

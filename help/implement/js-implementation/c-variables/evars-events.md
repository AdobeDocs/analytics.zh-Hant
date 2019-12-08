---
description: '如果您想要追蹤其他資訊，但沒有足夠的變數可以追蹤，現在可以存取其他eVar和成功事件 '
keywords: Analytics Implementation;evars;events;evars number;how many evars;how many events
title: 其他 eVar 和事件
topic: Developer and implementation
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 其他 eVar 和事件

如果您想要追蹤其他資訊，但沒有足夠的變數可以追蹤，現在可以存取其他eVar和成功事件：

> [!NOTE]JavaScript H-Code 不支援這些額外的 eVar 和事件。

## 自訂維度和事件的使用權限 {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Adobe Analytics 產品 |  |  |  |
|---|---|---|---|
| Adobe Analytics - Foundation | 75 個 prop | 200 個 eVar | 1000 個事件 |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 個 prop | 200 個 eVar | 1000 個事件 |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 個 prop | 200 個 eVar | 1000 個事件 |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 個 prop | 250 個 eVar | 1000 個事件 |

## 填入變數和事件 {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* 如果使用下列 [!DNL AppMeasurement] 版本，可將變數填入資料收集程式庫:

   * AppMeasurement for JavaScript 1.4+ 版
   * AppMeasurement for Flash 3.9+ 版
   * AppMeasurement for Java 1.2.8+ 版
   * AppMeasurement for Silverlight/.NET 1.4.2+ 版
   * AppMeasurement for PHP 1.2.2+ 版

* 如果您使用舊版代碼或 JavaScript H.*，您可填入上下文資料並使用處理規則來填入變數。
* 所有版本的資料收集代碼都能填入事件 101-1000。
* 可使用處理規則根據上下文資料或其他變數，填入 eVar 76-250。

## 常見問題集 {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **所有 Adobe Analytics 介面都能立即存取這些新變數嗎?**&#x200B;這些介面可立即存取: [!UICONTROL Analysis Workspace]、[!UICONTROL Reports &amp; Analytics]、[!UICONTROL Report Builder]、[!UICONTROL Ad Hoc Analysis]、API 和 [!UICONTROL Data Workbench]。

* **這些額外的 eVar 和事件會自動顯示在我的資料饋送中嗎?**&#x200B;新變數和事件啟用後，資料饋送即可存取這些變數和事件。新 eVar 欄必須由您選擇加入，才會顯示出來。但是，新事件一經啟用，就會立即顯示在event_list欄中，而事件查閱表格會包含這些事件ID的事件名稱。 除非您準備要在資料饋送中使用這些新事件，否則請勿將其啟用。

* **我如何請求新的資料饋送欄?**&#x200B;若想請求新欄，請參考[設定資料饋送](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html)。

* **我是 Analytics Ultimate 客戶，目前啟用了超過 200 個 eVar，若想改回使用 Analytics Prime 會發生什麼事?** Adobe 不會停用您任何現有的 eVar，但您無法再啟用新的 eVar。若您停用 eVar，須待您將已啟用的 eVar 降至 Analytics Prime 的限制 (200 個) 以下，才能再次啟用這些停用的eVar。


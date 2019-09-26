---
description: Configuration variables set in AppMeasurement.js.
keywords: Analytics 實作
seo-description: AppMeasurement.js for Adobe Analytics中的設定變數集
seo-title: 設定變數
solution: Analytics
subtopic: 變數
title: 設定變數
topic: 開發人員和實作
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# 設定變數概述

設定變數會控制資料在報表中擷取及處理的方式。The most-common configuration variables that are typically set in the main global JavaScript AppMeasurement.js). These variables can be set within the Analytics page-level code and links when appropriate.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. 其中有些設定變數可能不符合您的網站實施需求。

使用這些設定變數的部分目標為:

* 追蹤多個網站或網域。
* 在購買中使用任何貨幣。
* 擷取不同語言中的資料。
* 連結追蹤 (下載檔案數、外部網站連結。
* 因特殊目的追蹤自訂連結。

>[!NOTE]
>
>[!DNL AppMeasurement] 要求在對track函式的初始呼叫之前設定所有組態變數 `t()`。 如果在呼叫後設定組態變數，則可能 `t()`會發生非預期的結果。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

如需特定組態變數的說明，請參閱下列連結：

* [s_account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定資料儲存和報告的報表套裝。

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):根據每個頁面的URL動態選取報表套裝。

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定用於決定目標報表套裝的規則。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):使用DOM物件擷取套用所有規則之URL的區段。

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):部署動態填入變數的標幟。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):將傳入資料轉換為UTF-8，以便Analytics儲存和報告。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):確定套用至收入的轉換率。

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):決定設定和 `s_cc` Cookie `s_sq` 的網域。

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定頁面URL `s_cc` 網 `s_sq` 域中的句號數，以決定網域和Cookie。

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定由JavaScript(、`s_sq``s_cc`外掛程式)設定、原本即為第一方Cookie的Cookie，即使是第三方或網 `2o7.net` 域亦 `omtrdc.net` 然。

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):決定JavaScript和資料收集伺服器同時處理的Cookie有效期。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):請參考並允許在JavaScript檔案的適當位置呼叫函式。

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):函式，用作回呼（函式）和該函式的參數。

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):函式，用作回呼（函式）和該函式的參數。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):追蹤網站上可下載檔案的連結。

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):判斷所點按的任何連結是否為退出連結。

* [strackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):判斷是否收集ClickMap資料。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):包含以逗號分隔的副檔名清單。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):包含以逗號分隔的篩選器清單，這些篩選器代表屬於網站一部分的連結。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):判斷查詢字串是否應包含在「退出連結」和「檔案下載」報表中。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):包含隨自訂、退出和下載連結所傳送之變數的逗號分隔清單。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):用於報告退出連結的特定子集。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):在每個影 `s_doPlugins` 像要求之前呼叫函式。


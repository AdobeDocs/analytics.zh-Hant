---
description: AppMeasurement.js中設定的組態變數。
keywords: Analytics 實作
seo-description: AppMeasurement.js for Adobe Analytics中的設定變數集
seo-title: 設定變數
solution: Analytics
subtopic: 變數
title: 設定變數
topic: 開發人員和實作
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: a340bb50ec437db64dafaddc0b20aec740aee299

---


# 設定變數概述

設定變數會控制資料在報表中擷取及處理的方式。最常見的組態變數，通常設定在主要全域JavaScript appMeasurement.js中。 這些變數可在Analytics頁面層級程式碼和連結中設定（若適用）。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. 其中有些設定變數可能不符合您的網站實施需求。

使用這些設定變數的部分目標為:

* 追蹤多個網站或網域。
* 在購買中使用任何貨幣。
* 擷取不同語言中的資料。
* 連結追蹤 (下載檔案數、外部網站連結。
* 因特殊目的追蹤自訂連結。

>[!NOTE]
>
>[!DNL AppMeasurement] requires that all configuration variables are set before the initial call to the track function, `t()`. 如果在呼叫後設定組態變數，則可能 `t()`會發生非預期的結果。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

如需特定組態變數的說明，請按一下下列任一連結：

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Specify the report suite where data is stored and reported.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Dynamically select the report suite based on the URL of each page.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html):指定用於決定目標報表套裝的規則。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Use the DOM object to retrieve the section of the URL to which all rules are applied.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html):部署動態填入變數的標幟。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html):將傳入資料轉換為UTF-8，以便Analytics儲存和報告。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html):確定套用至收入的轉換率。

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html):決定設定和 `s_cc` Cookie `s_sq` 的網域。

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html):指定頁面URL `s_cc` 網 `s_sq` 域中的句號數，以決定網域和Cookie。

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html):指定由JavaScript(、`s_sq``s_cc`外掛程式)設定、原本即為第一方Cookie的Cookie，即使是第三方或網 `2o7.net` 域亦 `omtrdc.net` 然。

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html):決定JavaScript和資料收集伺服器同時處理的Cookie有效期。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html):請參考並允許在JavaScript檔案的適當位置呼叫函式。

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html):函式，用作回呼（函式）和該函式的參數。

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html):函式，用作回呼（函式）和該函式的參數。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html):追蹤網站上可下載檔案的連結。

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html):判斷所點按的任何連結是否為退出連結。

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html):判斷是否收集ClickMap資料。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html):包含以逗號分隔的副檔名清單。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html): Includes a comma-separated list of filters that represent the links that are part of the site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Determine whether or not the query string should be included in the Exit Links and File Download reports.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Include a comma-separated list of variables that are sent with custom, exit, and download links.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html):用於報告退出連結的特定子集。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html):在每個影 `s_doPlugins` 像要求之前呼叫函式。


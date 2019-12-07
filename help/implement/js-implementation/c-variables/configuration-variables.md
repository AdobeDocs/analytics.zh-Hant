---
description: 在 AppMeasurement.js 中設定的設定變數。
keywords: Analytics Implementation
subtopic: Variables
title: 設定變數
topic: Developer and implementation
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 設定變數概述

設定變數會控制資料在報表中擷取及處理的方式。最常見的組態變數，通常設定在主要全域JavaScript appMeasurement.js中。 您可視情況在 Analytics 頁面層級程式碼與連結內設定這些變數。

您透過&#x200B;**[!UICONTROL 管理員工具]** &gt; **[!UICONTROL 程式碼管理員]**&#x200B;產生程式碼時，並非所有這些變數都會預設出現於該程式碼中。其中某些組態變數可能不適用於您的網站實施需求。

使用這些設定變數的部分目標為:

* 追蹤多個網站／網域
* 在購買時使用任何貨幣
* 擷取不同語言的資料
* 連結追蹤（下載檔案數量、外部網站的連結）。
* 追蹤自訂連結以利於獨特用途

> [!NOTE][!DNL AppMeasurement] 要求所有設定變數都須於初始呼叫追蹤函數 `t()` 前設定。如果設定變數是在呼叫 `t()` 後設定，可能會發生未預期的結果。為確保資料收集正確，所有設定變數都須高於 `doPlugins` 函數。

如需特定組態變數的說明，請按一下下列任一連結：

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html):指定資料儲存和報告的報表套裝。

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html):根據每個頁面的URL動態選取報表套裝。

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html):指定用於決定目標報表套裝的規則。

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html):使用DOM物件擷取套用所有規則之URL的區段。

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html):部署動態填入變數的標幟。

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html):將傳入資料轉換為UTF-8，以便Analytics儲存和報告。

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html):確定套用至收入的轉換率。

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html):決定設定和 `s_cc` Cookie `s_sq` 的網域。

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html):指定頁面URL `s_cc` 網 `s_sq` 域中的句號數，以決定網域和Cookie。

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html):指定由JavaScript(、`s_sq``s_cc`外掛程式)設定、原本即為第一方Cookie的Cookie，即使是第三方或網 `2o7.net` 域亦 `omtrdc.net` 然。

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html):決定JavaScript和資料收集伺服器同時處理的Cookie有效期。

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html):請參考並允許在JavaScript檔案的適當位置呼叫函式。

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html):函式，用作回呼（函式）和該函式的參數。

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html):追蹤網站上可下載檔案的連結。

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html):判斷所點按的任何連結是否為退出連結。

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html):判斷是否收集ClickMap資料。

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html):包含以逗號分隔的副檔名清單。

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackintfilters.html):包含以逗號分隔的篩選器清單，這些篩選器代表屬於網站一部分的連結。

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html):判斷查詢字串是否應包含在「退出連結」和「檔案下載」報表中。

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html):包含隨自訂、退出和下載連結所傳送之變數的逗號分隔清單。

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html):用於報告退出連結的特定子集。

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html):在每個影 `s_doPlugins` 像要求之前呼叫函式。

* [s.useForcedlinkTracking](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-usedforcedlinktracking.html):停用某些瀏覽器的強制連結追蹤。

* [s.linkType](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktype.html):將連結類型設為下載、退出或自訂。

* [s.linkName](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkname.html):設定出現在下載、退出或自訂連結報表中的名稱。

* [s.ForcedlinkTrackingTimeout](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-forcedlinktrackingtimeout.html):設定追蹤時的最長等待時間。

* [s.linkTrackEvents](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackingevents.html):停用某些瀏覽器的強制連結追蹤。

* [s.linkUrl](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkurl.html):設定連結的URL。

* [s.linkObject](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkobject.html):引用已按一下的對象。

---
description: 指定退出連結，以及自訂連結的品牌化。造訪您網站的訪客可能會造訪資料收集網域的退出頁面，選擇不讓其活動在Adobe的分析產品中受到追蹤。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 新增選擇退出連結
topic: Developer and implementation
uuid: c12092be-3be7-4621-b838-d6b78d074f84
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 新增選擇退出連結

指定退出連結，以及自訂連結的品牌化。造訪您網站的訪客可能會造訪資料收集網域的退出頁面，選擇不讓其活動在Adobe的分析產品中受到追蹤。

如果使用者選擇不被追蹤並設定退出 Cookie，JavaScript 檔案仍會繼續傳送資料給 Adobe 伺服器，但不會處理或報告這些資料。

URL 結構的 collection_domain 區段是 JavaScript 檔案中使用的 trackingServer。Adobe Analytics實作所用的收集網域可在DigitalPulse除錯程式中的Adobe Analytics表格第一列中看到，該表格會依您的實作而標示為「第一方Cookie」或「第三方Cookie」。 您網站的收集網域可能包含 2o7.net、omtrdc.net 或您的網站網域，例如 metrics.example.com。

訪客可按一下退出頁面上的連結選擇退出，如此會在其瀏覽器中設定一個 Cookie。如果適用的追蹤網域中具有 `omniture_optout` Cookie，Adobe Analytics 就不會報告該使用者的活動。您可以提供自己的退出 Cookie 連結，也可以遵循下列步驟以設定退出 Cookie。

Adobe 提供所有實施類型的退出連結。您必須負責自己的隱私權原則以及遵循已簽署條款。請注意，退出頁面的連結會依您的實施類型而改變，如下所述。

如果您實施 Adobe Analytics 產品和服務並在 Adobe 擁有的網域 (亦即 207.net 或 omtrdc.net) 上設定 Cookie，則在針對 Adobe Analytics 產品和服務使用 Adobe Cookie 的所有網站上，可將您的訪客引導至 [Adobe 隱私中心](https://www.adobe.com/privacy/opt-out.html)提供的退出機制。Adobe 退出機制的直接連結為 `https:// *collection_domain* /optout.html`。

More information about Adobe Analytics privacy practices can be found at [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [退出頁面 URL 結構](/help/implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [退出 URL 範例](/help/implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [將退出 URL 品牌化](/help/implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## 退出頁面 URL 結構 {#section_E0462428D2E440E7863E24D2F6DBF748}

您的退出頁面位於下列 URL:

```
https://collection_domain/optout.html[?optional_parameters]
```

`optional_parameters` 包含:

`locale=[code]`: 提供選擇退出頁面的翻譯版本。支援下列地區設定:

* en_US (預設)
* de_DE
* es_ES
* fr_FR
* jp_JP
* ko_KR
* zh_CN
* zh_TW

`popup=1`:將頁面視為快顯視窗，並提供「關閉視窗」按鈕。

## 退出 URL 範例 {#section_258DE5226AA0483CA790D2C9C5318B2E}

完整視窗中的英文網頁包含一個連結，當按下此連結時可防止 metrics.example.com 上的訪客被追蹤:

```
https://metrics.example.com/optout.html
```

完整視窗中的法文網頁包含一個連結，當按下此連結時可防止 example.d3.sc.omtrdc.net 上的訪客被追蹤:

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

快顯視窗中的德文網頁包含一個連結，當按下此連結時可防止 example.112.2o7.net 上的訪客被追蹤:

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## 將退出 URL 品牌化 {#section_674AB62E810B414AB8F1615C0E3061F8}

您可以在網站某處提供類似下列的連結:

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

其中&#x200B;*`stats.adobe.com`* 會取代為 *`s.trackingServer`* 變數所設定的任何值。

此外，如果您想提供退出的連結，請使用同一個 URL 但將 `?optout=1` 更換為 `?optin=1`，並保留 `confirm_change=1`。

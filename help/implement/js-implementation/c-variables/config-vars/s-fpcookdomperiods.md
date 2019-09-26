---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.fpCookieDomainPeriods

 變數會用於由 JavaScript (s_sq、s_cc、外掛程式) 設定、原本即為第一方 Cookie 的 Cookie，即使您的實施使用第三方 2o7.net 或 omtrdc.net 網域亦然。

The *`fpCookieDomainPeriods`* variable should never be dynamically set . 如果您使 *`cookieDomainPeriods`*&#x200B;用，也建議您為指定值 *`fpCookieDomainPeriods`* 。 *`fpCookieDomainPeriods`* inherits the  value. *`cookieDomainPeriods`* Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

名稱" *`fpCookieDomainPeriods`*"是指句點數("。")"www" 開頭時位於網域中的句號 (.) 數。For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

JavaScript [!DNL AppMeasurement] 檔案使用變 *`fpCookieDomainPeriods`* 數來判斷要用來設定訪客ID  (s_vi)Cookie以外第一方Cookie的網域。 There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). 此外，[!UICONTROL getValOnce] 之類的外掛程式所使用的 Cookie 也會受影響。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | cookieDomainPeriods |

## 用以設定 Cookie 網域變數的範例程式碼

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## 語法和可能的值

 此&#x200B;*`cookieDomainPeriods`* 變數應為字串，如下所示。

```js
s.fpCookieDomainPeriods="3"
```

## 範例

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## 組態設定

無
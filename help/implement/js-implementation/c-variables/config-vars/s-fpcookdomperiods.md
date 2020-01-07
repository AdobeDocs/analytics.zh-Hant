---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.fpCookieDomainPeriods

 變數會用於由 JavaScript (s_sq、s_cc、外掛程式) 設定、原本即為第一方 Cookie 的 Cookie，即使您的實施使用第三方 2o7.net 或 omtrdc.net 網域亦然。

*`fpCookieDomainPeriods`* 變數絕不可動態設定。如果您使用 *`cookieDomainPeriods`*，為 *`fpCookieDomainPeriods`* 指定值也是不錯的做法。*`fpCookieDomainPeriods`* 會繼承 *`cookieDomainPeriods`* 值。請注意，*`fpCookieDomainPeriods`* 不會影響訪客 ID Cookie 設定所在的網域，即使您的實施將此 Cookie 視為第一方 Cookie 亦然。

名稱 「*`fpCookieDomainPeriods`*」代表網域以"www" 做為開頭時位於網域中的句號 (".") 數。例如，`www.mysite.com` 包含兩個句號，`www.mysite.co.jp` 則包含三個句號。此變數還有另一種解釋方式，即網站之主網域的區段數 (`mysite.com` 為兩個區段，`mysite.co.jp` 為三個區段)。

JavaScript 檔案適用的 [!DNL AppMeasurement] 會使用 *`fpCookieDomainPeriods`* 變數來判斷要透過哪個網域設定第一方 Cookie，但 [!UICONTROL 訪客 ID] (s_vi) Cookie 除外。至少有兩個 Cookie 會受此變數影響，包括 `s_sq` 與 `s_cc` (分別用於訪客點擊對應和 Cookie 檢查)。此外，[!UICONTROL getValOnce] 之類的外掛程式所使用的 Cookie 也會受影響。

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

*`cookieDomainPeriods`* 變數應為字串，如下所示。

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

---
description: 行動追蹤代碼會以伺服器產生的影像標記的形式放置在頁面上。
keywords: Analytics Implementation;mobile tracking;mobile protocols;prevent caching;alt tag;default image type
title: 標記行動通訊協定的頁面
topic: Developer and implementation
uuid: 5788beaf-f309-4918-a99c-a3e591668205
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 標記行動通訊協定的頁面

行動追蹤代碼會以伺服器產生的影像標記的形式放置在頁面上。

行動追蹤代碼會以伺服器產生的影像標記的形式放置在頁面上。由於 JavaScript 和 WMLScript 等指令碼語言並未在各種行動裝置間普遍受到支援，因此無法透過指令碼語言動態產生追蹤信標。

雖然行動信標影像實際為 2x2 像素，但為了確保支援所有行動裝置，您應將高度和寬度屬性設為 5。例如:

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## 使用隨機數字防止快取 {#section_BF5C344A16034C439C8704632CF673A7}

雖然 Adobe 伺服器會指示瀏覽器不要快取追蹤信標，但不見得所有的瀏覽器都會遵循這些指示。若要進一步防止信標快取，建議您讓 Web 伺服器在影像 URL 路徑中動態產生隨機數字。如此將可進一步確保報告的正確性。隨機數字應位於路徑的最後一個區段中，如下所示: 

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## 包含 ALT 標記 {#section_FBD8B2FD1EA0429580C2B933DA300B07}

有些行動瀏覽器會要求所有的影像皆必須在影像標記中加入 alt 文字。以下是 ALT 屬性在影像標記中的顯示情形: 

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

/5/ 務必要一律正確出現在路徑中。Adobe 伺服器會使用此項目來識別行動裝置。若使用標準 /1/，Adobe 伺服器將會嘗試在行動裝置上設定 Cookie。

## 變更預設影像類型 {#section_2F969909010D4A64BF6E092A32ABADB7}

如果某個裝置不支援預設影像類型，則不會傳回任何資料。為了避免這種情形，您可以強制 Adobe 資料收集伺服器傳回行動裝置支援的特定圖形類型。報表套裝名稱之後的程式碼會指定影像類型:

* `/5/` 會傳回預設影像類型。
* `/5.1/` 或 `/1/` 一律會傳回 GIF 影像。

* `/5.5/` 一律會傳回 WBMP 影像。

請參閱[識別使用行動通訊協定的訪客](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md)。

---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# referrer

此變數可用來還原遺失的反向連結資訊。


<!-- 

referrer.xml

 -->

伺服器端和 JavaScript 重新導向通常用於將訪客引導到合適的位置。但是，當瀏覽器被重新導向後，會遺失原始反向連結 URL。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 255 位元組 | R | 流量 &gt; 尋找方法轉換 &gt; 尋找方法 | document.referrer |

許多公司會在其網站間的許多位置使用重新導向。例如，搜尋引擎付費搜尋結果的重新導向可能會帶來訪客。當瀏覽器重新導向後，通常會遺失反向連結。此&#x200B;*`referrer`* 變數可在重新導向後，用來還原第一個頁面上的原始 *`referrer`* 值。*`referrer`* 可在伺服器端填入，或經由查詢字串的 JavaScript 填入。

反向連結必須屬於「正常格式」，Analytics 才能加以記錄，也就是說，必須遵循標準 URL 格式，具有通訊協定和適當位置。

**語法和可能的值** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

此 *`referrer`*.請確保字串是 URL 編碼的 (無空格)。

**範例** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**組態設定** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

無

**缺陷、問題和提示** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

*`referrer`* 必須是標準 URL，且包含通訊協定。

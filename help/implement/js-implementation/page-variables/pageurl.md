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


# pageURL

 變數會覆寫頁面的實際 URL。


<!-- 

pageURL.xml

 -->

極少數的情況下，頁面的 URL 不會是您要在 Analytics 中報告的 URL。

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 不限* </td> 
   <td> <p>G </p> </td> 
   <td> 流量 &gt; 區段 &gt; 最受歡迎頁面的路徑 </td> 
   <td> 頁面 URL </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE]雖然 Adobe 可允許高達 64k 的 *`pageURL`* 值，但有些瀏覽器會對影像要求的 URL 施加大小限制。為了防止截斷其他資料，長度超過 255 個位元組的 URL 會遭到切割，前 255 個位元組出現在 `g=` 參數，其餘位元組出現在 `-g=` 查詢參數的查詢字串中。

**語法和可能的值** {#section_22AF3BF7C2F743549967B0C760A095C0}

*`pageURL`* 變數必須是有效的 URL，且具備有效的通訊協定。根據 Analytics 設定，網域在填入至報表之前會強制以小寫顯示，且查詢字串可能會遭到清除。

```js
s.pageURL="proto://domain/path?query_string"
```

僅允許與 URL 相容的字元作為頁面 URL。

> [!NOTE]將 *`pageURL`* 變數用於自訂用途前，強烈建議您先聯絡 Adobe 顧問或客戶服務。

**範例** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**組態設定** {#section_A8F77DAD88164528ACC5C16C066B47DF}

無


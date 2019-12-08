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


# pageType

 變數的用途僅止於指定 404 (找不到頁面) 錯誤頁面。


<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
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
   <td> 20 位元組 </td> 
   <td> pageType </td> 
   <td> 路徑 &gt; 頁面 &gt; 找不到頁面 <p>找不到 </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. 在錯誤頁面上正確地設定 *`pageType`* 變數，如下所示。

請勿在 404 錯誤頁面上使用頁面名稱變數。此&#x200B;*`pageType`* 變數只會用於 404 錯誤頁面。

在大部分的情況下，404 錯誤頁面會是硬式編碼的靜態頁面。在這種情況下，請務必將 .JS 檔案的參考設為適當的全域或相對路徑/目錄。

**語法和可能的值** {#section_C1C59968226446559B05F6EE7374D525}

唯一允許的 *`pageType`* 值為「errorPage」，如下所示。

```js
s.pageType="errorPage"
```

**範例** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**組態設定** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

無

**缺陷、問題和提示** {#section_943681AB01FE47BEAC72E93CB60C53C8}

若要擷取其他伺服器端錯誤 (例如 500 錯誤)，請使用 prop 擷取錯誤訊息，並將「`500 Error: <URL>`」(其中 `<URL>` 是要求的 URL) 放入 *`pageName`* 變數中。在執行這些動作後，您即可使用[!UICONTROL 「路徑分析」]報表來檢視是哪些路徑導致使用者產生 500 錯誤。此 prop 會說明哪個錯誤訊息是伺服器所發出的。


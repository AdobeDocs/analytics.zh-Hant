---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---



# linkName

此變數是用於[!UICONTROL 連結追蹤]中的選用變數，可決定自訂、下載或退出連結的名稱。


<!-- 

linkName.xml

 -->

在一般情況下不會使用 *`linkName`* 變數，因為此變數會由 *`tl()`* 函數中的第三個參數取代。

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 位元組 </td> 
   <td> pev2 </td> 
   <td> <p>檔案下載 </p> <p>自訂連結 </p> <p>退出連結 </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 「自訂連結」]是指傳送追蹤資料的連結。此&#x200B;*`linkName`* 變數 (或 *`tl()`* 函數中的第三個參數) 可用來識別出現在[!UICONTROL 自訂]、[!UICONTROL 下載]或[!UICONTROL 退出連結]報表中的值。若未填入 *`linkName`*，則連結的 URL 會出現在報表中。

**語法和可能的值** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

除了標準變數限制以外，*`linkName`* 並無其他限制。

**範例** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**組態設定** {#section_F15FF429FC274F708D50DF79D4668EA3}

無

**缺陷、問題和提示** {#section_170A78452A7340B5B229713AC1FB71FA}

* *`linkName`* 變數會由 *`tl()`* 函數中的第三個參數取代。

* 如果 *`linkName`* 變數和 *`tl()`* 函數中的第三個參數為空白，則連結的完整 URL (查詢字串除外) 會顯示在報表中 (即使該連結為相對連結)。

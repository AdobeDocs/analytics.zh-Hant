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


# pageName

 變數包含您的網站上各個頁面的名稱。


<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> pageName </td> 
   <td> <p>頁面 </p> <p>路徑 </p> </td> 
   <td> 頁面 URL </td> 
  </tr> 
 </tbody> 
</table>

此&#x200B;*`pageName`* 變數中應填入商業使用者可辨識的值。在大多數情況下，*`pageName`* 值不會是 URL 或檔案路徑。常見的 *`pageName`* 值包括「首頁」、「結帳」、「感謝您購買」或「註冊」等名稱。

請留意勿讓新行字元、長破折號/短破折號或任何 HTML 字元出現在頁面名稱和其他變數中。有些瀏覽器會傳送新行字元，有些則否，這會使 Analytics 中的資料在兩個看似相同的頁面名稱之間出現歧異。有許多文字處理器和電子郵件用戶端會在您鍵入時自動將連字號轉換為短破折號或長破折號。由於短破折號和長破折號在 Analytics 變數中屬於非法字元 (字元碼超過 127 的 ASCII 字元)，Analytics 將不會記錄含有非法字元的頁面名稱，而會改為顯示 URL。

如果將 *`pageName`* 保留為空白，則會以 URL 表示頁面名稱。將 *`pageName`* 保留為空白常會造成問題，因為同一個頁面的 URL 不一定都會相同 (`www.mysite.com` 與 `mysite.com` 是具有不同 URL 的相同頁面)。

**語法和可能的值** {#section_7A61EE70F1A84D26B414404998C84BA8}

*`pageName`* 變數應包含對 Analytics 的商業使用者具有參考價值的識別碼。

```js
s.pageName="page_name"
```

除了標準變數限制以外，*`pageName`* 並無其他限制。

**範例** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**組態設定** {#section_58CBC68C805344A999EB47455FEBA8D5}

管理員可在 Analytics 中使用[!UICONTROL 「命名頁面」]工具變更可見的頁面名稱，但這隱含潛在風險，且可能對您的報表造成負面影響。使用「命名頁面」工具前，請先與 Adobe [!UICONTROL 客戶服務]連絡。

**缺陷、問題和提示** {#section_BB41DC9682C34385B9CAA80D5257C113}

確認 *`pageName`* 未包含非法字元。

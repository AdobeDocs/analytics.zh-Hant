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



# linkType

 變數是一個用於連結追蹤中的可選變數，可判斷會出現連結名稱或 URL 的報表 (自訂、下載或退出連結)。


<!-- 

linkType.xml

 -->

在一般情況下不會使用 *`linkType`* 變數，因為此變數會由 *`tl()`* 函數中的第二個參數取代。

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> 一個字元 </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>檔案下載 </p> <p>自訂連結 </p> <p>退出連結 </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

自訂連結會將資料傳送至 Analytics。*`linkType`* 變數 (或 *`tl()`* 函數中的第二個參數) 可用來識別將出現連結名稱或 URL 的報表 ( [!UICONTROL 自訂]、[!UICONTROL 下載]或[!UICONTROL 退出連結]報表)。

對於退出連結和下載連結，系統會根據點按的連結是否為退出連結或下載連結，自動填入 *`linkType`* 變數。自訂連結可在設定後，透過此變數或 *`tl()`* 函數中的第二個參數，傳送至這三個報表的任何一個。將 *`linkType`* 設定為「o」、「e」或「d」後，*`linkName`* 或連結 URL 會分別傳送至[!UICONTROL 自訂連結]、[!UICONTROL 退出連結]或[!UICONTROL 檔案下載]報表。

**語法和可能的值** {#section_18DB3A8083FB4F75B970055ED336DA4E}

*`linkType`* 變數語法取決於您使用 XML 或查詢字串。

若使用 XML，變數可能僅會包含單一字元 (即「o」、「e」或「d」)。

```js
s.tl(this,'o','Link Name');
```

若使用查詢字串 `pe`，則您需要使用 `lnk_d`、`lnk_e` 或 `lnk_o`。

**範例** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**組態設定** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

無

**缺陷、問題和提示** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* 若未指定 *`linkType`*，則會假設為自訂連結 (「o」)。

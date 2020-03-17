---
description: 顯示訪客最常存取的網站區域。「網站區域」可包含您定義的產品群組 (類似於類別)。例如，您可能有頁面的「相機」群組、「電腦」群組等。「轉換網站區域」報表的資料是從「流量」群組中的「網站區域」報表匯入，「網站區域」報表則是從追蹤程式碼中的頻道變數接收資訊。您可以使用此報告識別不同網站區域的項目對網站統計資料的最大影響。
title: 網站區域
topic: Reports
uuid: 6839c566-f88f-4979-9cf5-52a77c0b0416
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 網站區域

顯示訪客最常存取的網站區域。「網站區域」可包含您定義的產品群組 (類似於類別)。例如，您可能有頁面的「相機」群組、「電腦」群組等。「轉換網站區域」報表的資料是從「流量」群組中的「網站區域」報表匯入，「網站區域」報表則是從追蹤程式碼中的頻道變數接收資訊。您可以使用此報告識別不同網站區域的項目對網站統計資料的最大影響。

* 此報告會直接參照來自於網站上實作之 [s.channel](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_channel.html) 變數的資料。
* 此報告可使用趨勢與排名格式來檢視。
* 此報告可使用搜尋篩選器尋找特定明細項目。
* 您可以在此報告中使用「 分類」，以便對明細項目重新命名和合併。
* 關聯可透過「管理工具」以任何其他流量變數來建立。
* 此報告可使用下列量度：

   * **頁面檢視**：[pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) 變數或 URL 已定義 (設為預設量度) 的次數

   * **所有路徑量度**：瀏覽、平均頁面深度、平均頁面逗留時間、登入點、退出點、重新載入與單次存取
   * 根據您的組織與報表套裝的設定：可在此報告上啟用每日、每週、每月、每季獨特訪客。
   * **所有標準電子商務量度**：收入、訂購、件數、購物車、購物車檢視、結帳、購物車新增、購物車移除等
   * **所有自訂事件**：事件 1-80；使用 H22 程式碼或更高版本時則為事件 81-100。

[!UICONTROL 網站區域報告]中的所有轉換事件都會使用最後一個配置。您會看到轉換劃分到實作中不含成功事件的各個頁面。這不同於使用線性配置的[頁面報告](/help/components/c-variables/dimensionslist/reports-pages.md)。

**產品特定資訊**

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 介面 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 網站內容</span> &gt; <span class="uicontrol">網站區域</span> </p> <p>除了關聯以外，此報告也可使用下列劃分： </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">任何以此報告為基礎的分類報告 </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> 追蹤程式碼報告</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> <span class="wintitle"> 產品</span>與<span class="wintitle">類別</span>報告 </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> 客戶忠誠度報告</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">任何完全子關聯的轉換變數 </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> 首次接觸與最後一次接觸行銷管道</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> <span class="uicontrol"> Target</span> &gt; <span class="uicontrol">促銷活動</span>報告 (若已啟用) </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">每次瀏覽逗留時間 </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">網站區域 </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">登入頁面 </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">多數流量來源報告 </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">訪問次數 </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">多種訪客資料報告 </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">所有轉換變數與清單變數 </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">可使用瀏覽以及每日、每週、每月、每季、任意獨特訪客。 </li> 
      </ul> </li> 
    </ul> <p>此報告可使用區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Ad Hoc Analysis 可透過行銷報告介面中的幾乎所有其他報表，來劃分「網站區域」報表。 </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">除了所有前述的事件外，也可使用所有的轉換與流量量度，並可對各種轉換量度使用不同的配置。 </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">此報告可使用多個高度進階區段。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>


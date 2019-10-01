---
description: 列出可在Adobe整合精靈的步驟4中提供的可選維度識別碼。
seo-description: 列出可在Adobe整合精靈的步驟4中提供的可選維度識別碼。
seo-title: Demandbase自訂維度
title: Demandbase自訂維度
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Demandbase自訂維度{#demandbase-custom-dimensions}

列出可在Adobe整合精靈的步驟4中提供的可選維度識別碼。

如果您不確定要進入精靈的確切API ID，請洽詢您的Demandbase代表。

>[!IMPORTANT]
>
>強烈建議您不要將IP位址加入自訂維度。 唯一值的數目極多，可能會造成報告的效能問題。 此外，IP位址已透過Adobe資料倉庫報告提供為報告選項。

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 維度 </th> 
   <th colname="col2" class="entry"> API ID </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> 指出所識別的組織是否分類為ISP。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行銷別名 </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> 已清除和／或縮短組織名稱（32個字元或更短），以用於廣告、訊息或行銷文案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 帳戶監控標籤 </td> 
   <td colname="col2"> watch_list（自訂） </td> 
   <td colname="col3">由用戶端定義的不限標籤集，可依組織新增至其API回應資料。 <p><b>範例</b>:如果您有名為Q4 Target的「監看標籤」,API欄位將會 </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 財富1000強 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> 指出該組織是否列在《財富》1000強名單中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 福布斯2000年 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> 指出該組織是否在福布斯2000名單中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 員工計數 </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> 該組織雇用的人數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年度銷售 </td> 
   <td colname="col2"> 年度銷售 </td> 
   <td colname="col3"> 對於公共實體，年度收入是根據公司報告的所有地點的全球總部公共記錄。 對於私營組織，則以年度銷售收入數的共識估計為基礎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 電話號碼 </td> 
   <td colname="col2"> 手機 </td> 
   <td colname="col3"> 組織的電話號碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 街道地址 </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> 組織的街道地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> 城市 </td> 
   <td colname="col3"> 該組織的城市已查明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 狀態 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 已確定組織的狀態。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 國家/地區代碼 </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> 組織的ISO兩字元國家／地區代碼已識別。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 國家/地區名稱 </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> 已識別組織的國家／地區字串值國家／地區名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 已識別組織的國家／州的郵遞區號。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 網站 </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> 組織所識別的URL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 股票行情 </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> 如果已識別的組織是公開交易的，股票行情會變得更糟。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主要SIC代碼 </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> 已識別為組織分配的合意SIC代碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 緯度 </td> 
   <td colname="col2"> 緯度 </td> 
   <td colname="col3"> 確定的組織所在位置的Latitude。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 經度 </td> 
   <td colname="col2"> 經度 </td> 
   <td colname="col3"> 已識別組織位置的經度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> 流量 </td> 
   <td colname="col3"> 網站流量，估計為低、中或高或極高。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 指出已識別的公司主要銷售給其他企業。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 指出已識別的公司主要銷售給消費者或個人。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Technology Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 客戶透過類別、廠商和產品定義最多75個技術類別，以用於定位和／或自訂廣告、訊息或行銷文案。 </td> 
  </tr> 
 </tbody> 
</table>


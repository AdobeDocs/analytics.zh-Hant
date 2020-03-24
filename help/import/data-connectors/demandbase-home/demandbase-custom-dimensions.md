---
description: 列出可在 Adobe 整合精靈的步驟 4 中提供的選用維度識別碼。
title: Demandbase 自訂維度
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Demandbase 自訂維度{#demandbase-custom-dimensions}

列出可在 Adobe 整合精靈的步驟 4 中提供的選用維度識別碼。

如果您不確定要輸入精靈的確切 API ID，請洽詢您的 Demandbase 代表。

>[!IMPORTANT]
>
>強烈建議您不要包含 IP 位址作為自訂維度。唯一值的數量極多，可能會造成報表的效能問題。此外，已透過 Adobe Data Warehouse 報表提供 IP 位址作為報表選項。

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
   <td colname="col3"> 指出所識別的組織是否分類為 ISP。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行銷別名 </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> 已清理和/或已縮短組織名稱 (32 個字元或更短)，以用於廣告、訊息或行銷文案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 帳戶監看標籤 </td> 
   <td colname="col2"> watch_list (自訂) </td> 
   <td colname="col3">由用戶端定義的無限標籤集，可供組織新增至其 API 回應資料。 <p><b>範例</b>：如果您有名為「Q4 Target」的監看標籤，則 API 欄位會是 </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 《財富》1000 大 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> 指出該組織是否列於《財富》1000 大名單中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 《富比士》2000 大 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> 指出該組織是否列於《富比士》2000 大名單中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 員工人數 </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> 該組織雇用的人數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年度銷售額 </td> 
   <td colname="col2"> annual_sales </td> 
   <td colname="col3"> 對於公共實體而言，年度收入是根據公司針對全球所有總部地點報告的公共記錄而定。對於私人組織而言，年度收入則是以年度銷售額收入的共識預測為基礎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 電話號碼 </td> 
   <td colname="col2"> phone </td> 
   <td colname="col3"> 已識別之組織的電話號碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 街道地址 </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> 已識別之組織的街道地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> 已識別之組織的城市。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 狀態 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 已識別之組織的州。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 國家/地區代碼 </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> 已識別之組織的 ISO 2 字元國家/地區代碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 國家/地區名稱 </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> 已識別之組織的國家/地區的國家/地區名稱字串值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 已識別之組織的國家/州的郵遞區號。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 網站 </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> 已識別之組織使用的 URL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 股票代號 </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> 股票代號 (如果已識別之組織是上市公司)。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主要 SIC 碼 </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> 指派給已識別之組織的共識 SIC 碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 緯度 </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> 已識別之組織所在位置的緯度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 經度 </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> 已識別之組織所在位置的經度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> traffic </td> 
   <td colname="col3"> 網站流量，估計為低、中、高或極高。 </td> 
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
   <td colname="col1"> 技術深入分析 </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 由客戶透過類別、廠商和產品來定義高達 75 個技術類別，以用於目標定位和/或自訂廣告、訊息或行銷文案。 </td> 
  </tr> 
 </tbody> 
</table>


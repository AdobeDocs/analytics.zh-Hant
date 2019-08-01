---
description: 列出可在Adobe整合精靈步驟中指定的選用維度識別碼。
seo-description: 列出可在Adobe整合精靈步驟中指定的選用維度識別碼。
seo-title: Demandbase自訂維度
title: Demandbase自訂維度
uuid: d162104-1aa2-46b9-a536-4a8 fb792 b69 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

列出可在Adobe整合精靈步驟中指定的選用維度識別碼。

如果您不確定正確的API ID是否要進入精靈，請與您的Demandbase代表諮詢。

>[!IMPORTANT]
>
>強烈建議您不要將IP位址納入自訂維度。極少的唯一值可能會造成報告效能問題。此外，IP位址已透過Adobe資料倉庫報告提供作為報告選項。

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
   <td colname="col2"> ISP </td> 
   <td colname="col3"> 指出所識別的組織是否已分類為ISP。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marketing Alias </td> 
   <td colname="col2"> marketing_ alias </td> 
   <td colname="col3"> 已清理及/或縮短組織名稱(32個字元或較少)用於廣告、訊息或行銷文案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 帳戶監控標記 </td> 
   <td colname="col2"> patch_ list(自訂) </td> 
   <td colname="col3">由用戶端定義的無限制標籤集，可依組織的要求新增至其API回應資料。 <p><b>範例</b>：如果您有一個名為Q Target的Watch標記，API欄位將會是 </p> <code> patch_ list_ q4_ target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 財星1000 </td> 
   <td colname="col2"> 財星_1000 </td> 
   <td colname="col3"> 指出該組織是否列入財星1000大清單。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes2000 </td> 
   <td colname="col2"> fores_2000 </td> 
   <td colname="col3"> 指出組織是否位於Forbes2000清單中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 員工計數 </td> 
   <td colname="col2"> employee_ count </td> 
   <td colname="col3"> 組織雇用的人數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年度銷售 </td> 
   <td colname="col2"> annual_ sales </td> 
   <td colname="col3"> 對於公共實體，年度收入是根據公司在所有地點的全域HQ公開記錄。對於私人組織，則是根據每年銷售收入數字的一致預估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 電話號碼 </td> 
   <td colname="col2"> 手機 </td> 
   <td colname="col3"> 組織的電話號碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 街道地址 </td> 
   <td colname="col2"> street_ address </td> 
   <td colname="col3"> 組織的街道地址已識別。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> 城市 </td> 
   <td colname="col3"> 組織所識別的城市。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 狀態 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 組織的狀態已識別。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 國家/地區代碼 </td> 
   <td colname="col2"> country_ code </td> 
   <td colname="col3"> 組織的ISO兩字元國家/地區代碼識別。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 國家/地區名稱 </td> 
   <td colname="col2"> country_ name </td> 
   <td colname="col3"> 組織的字串值國家/地區名稱識別。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 郵遞區號 </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 組織所識別之國家/地區的郵遞區號。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 網站 </td> 
   <td colname="col2"> web_ site </td> 
   <td colname="col3"> 組織所用的URL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stock Timer </td> 
   <td colname="col2"> stock_ atiker </td> 
   <td colname="col3"> 如果所識別的組織是公開交易，則股票行情會出現。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主要SIC程式碼 </td> 
   <td colname="col2"> master_ sic </td> 
   <td colname="col3"> 已為組織指定一致的SIC代碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 緯度 </td> 
   <td colname="col2"> 經緯度 </td> 
   <td colname="col3"> 組織所識別位置的緯度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 經度 </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> 組織所識別位置的發行者。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> 流量 </td> 
   <td colname="col3"> 網站流量的量，估計為低、中等、高或極高。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 指出已識別的公司主要銷售給其他業務。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 指出已識別的公司主要銷售給消費者或個人。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Technology Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 客戶透過類別、廠商和產品定義的75種技術類別，用於使用定位及/或自訂廣告、訊息或行銷文案。 </td> 
  </tr> 
 </tbody> 
</table>


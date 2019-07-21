---
description: 量度是採用標準、參與率、最近和線性配置方法來計算。每個方法依據公式不同，計算的值也不同。
seo-description: 量度是採用標準、參與率、最近和線性配置方法來計算。每個方法依據公式不同，計算的值也不同。
seo-title: 度量計算
solution: Analytics
title: 度量計算
topic: 量度
uuid: 2af58f1e-12c5-4828-ae39-c9 eaef6 b705
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 度量計算

量度是採用標準、參與率、最近和線性配置方法來計算。每個方法依據公式不同，計算的值也不同。

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度計算 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 原始 </td> 
   <td colname="col2"> <p>會給予第一個與成功事件關聯的變數值滿分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最近 </td> 
   <td colname="col2"> <p>會給予最近一個與成功事件關聯的變數值滿分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 線性 </td> 
   <td colname="col2"> <p>選取線性分配時，成功事件將平均分配給同一次瀏覽中所看到的所有變數值。若是數值和貨幣事件 (如<span class="term"> 收入</span>，則會劃分貨幣金額。For counter events such as <span class="term"> Orders</span>, a fraction of the event is awarded to each variable value in the visit. 並在報告時加總這些部分的分數，四捨五入到最接近的整數。 </p> <p>例如，若某次存取在一個成功事件前瀏覽了 4 個頁面，則每個頁面會收到該事件 25% 的評分。如果在同一次瀏覽中，<span class="varname"> 促銷活動</span> 有兩個值，每個促銷活動值會收到該事件50%的評分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參與率 </td> 
   <td colname="col2"> <p>對同一次瀏覽中促成成功事件的每個值指派滿分。如果您使用跨瀏覽參與率量度，則此計算也能跨訪客作業階段而套用。 </p> <p>See <a href="../../../components/c-variables/c-metrics/metrics-participation.md#concept_8E6B39106A244CB49E055150B291B477" format="dita" scope="local"> Participation</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例 - 量度計算 {#section_4CE01DA35108418D9909823A7ECC4B45}

假設您的網站有內部搜尋，並使用轉換變數 (eVar) 加以追蹤。訪客執行了數個內部搜尋，之後購買了 $100 元商品:

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt;購買$100

在報告中，評分分配如下: 

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar 值 </th> 
   <th colname="col2" class="entry"> 第一個 </th> 
   <th colname="col3" class="entry"> 最後一個 </th> 
   <th colname="col4" class="entry"> 線性 </th> 
   <th colname="col5" class="entry"> 參與率 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>寵物 </p> </td> 
   <td colname="col2"> <p>$100 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>貓科 </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>貓 </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$0 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>小貓 </p> </td> 
   <td colname="col2"> <p>$0 </p> </td> 
   <td colname="col3"> <p>$100 </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>$100 </p> </td> 
  </tr> 
 </tbody> 
</table>


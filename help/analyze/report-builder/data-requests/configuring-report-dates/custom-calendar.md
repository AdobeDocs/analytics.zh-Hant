---
description: Report Builder 使用 Analytics 自訂日曆。您可以使用日曆來定義一週和一年的第一天，或使用其他零售日曆類型。日曆格式的作用各異，包括銷售比較和預測標準化，工資成本分析或實地盤存規範。
solution: Analytics
title: 自訂日曆
topic: Report builder
uuid: 88d24bf9-de46-41e0-937e-b8a1fe36c55d
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 自訂日曆

Report Builder 使用 Analytics 自訂日曆。您可以使用日曆來定義一週和一年的第一天，或使用其他零售日曆類型。日曆格式的作用各異，包括銷售比較和預測標準化，工資成本分析或實地盤存規範。

以下詳細介紹各種日曆格式。

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日曆 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>西曆 </p> </td> 
   <td colname="col2"> <p> 使用傳統的日曆格式 (一月到十二月，每月 30 或 31 天，以及每月不同的週數)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已修改的西曆 </p> </td> 
   <td colname="col2"> <p> 使用傳統西曆，但可讓您選擇每年的第一個月，以及每週的第一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4 零售日曆 </p> </td> 
   <td colname="col2"> <p> 將每月按當月的週數劃分。亦即一月有四週，依此類推。全美零售商聯合會使用的就是 4-5-4 日曆格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂日曆 </p> </td> 
   <td colname="col2"> <p> 根據每個月的週數提供三種格式。每月週數視乎當年所選的第一天而定。 </p> <p>一年有 52 週。將總週數分為 4 季，則每季有 13 週。但每季有 3 個月。13不能被3除掉，因此，你最後將多一週投入其中一個月，這樣一來就始終如一。 5/4/4 指的是多出來的那一週放到該季的第 1 個月。4/5/4 指的是多出來的那一週放到該季的第 2 個月，以此類推。在 5-4-4 日曆中，第 53 週會新增至該年的最後一季中。 </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>: 一月有四週，二月有五週，三月有四週，以此類推。 </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: 一月有四週，二月有四週，三月有五週，以此類推。 </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: 一月有五週，二月有五週，三月有四週，以此類推。 </li> 
    </ul> <p>注意: 除了不支援自訂日曆的 Data Warehouse 外，其他所有 Adobe Analytics 工具 (Analysis Workspace、Reports &amp; Analytics、Report Builder、Activity Map、Ad Hoc Analysis) 皆支援此日曆選項。 </p> </td> 
  </tr> 
 </tbody> 
</table>


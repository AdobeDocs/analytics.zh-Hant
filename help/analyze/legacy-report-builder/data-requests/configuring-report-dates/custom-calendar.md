---
description: Report Builder使用Analytics自訂日曆。 您可以使用行事曆來定義一週和一年的第一天，或使用不同的零售行事曆樣式。 工作歷格式可用於各種用途，包括銷售比較與預測標準化、給薪成本分析或實際盤點盤點規則。
title: 自訂日曆
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
TQID: https://experienceleague.adobe.com/At3YiOPV0jx5WXwe-VvA05n3yIEmiAJIRzoOoeISeA4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 28%

---

# 自訂日曆

{{legacy-arb}}

Report Builder使用Analytics自訂日曆。 您可以使用行事曆來定義一週和一年的第一天，或使用不同的零售行事曆樣式。 工作歷格式可用於各種用途，包括銷售比較與預測標準化、給薪成本分析或實際盤點盤點規則。

每種行事曆格式說明如下。

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 行事曆 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>西曆 </p> </td> 
   <td colname="col2"> <p> 使用傳統行事曆格式（一月到12月，包含30或31天以及每個月的可變周數）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已修改的西曆 </p> </td> 
   <td colname="col2"> <p> 使用傳統西曆，但可讓您選取一年的第一個月和一週的第一天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4零售日曆 </p> </td> 
   <td colname="col2"> <p> 每月以當月的周數劃分。 也就是說，一月有四周，以此類推。 National Retail Federation使用4-5-4行事曆格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂日曆 </p> </td> 
   <td colname="col2"> <p> 根據每個月的周數提供三種格式。 每月週數取決於當年所選的第一天。 </p> <p>一年有52週。 將其分為4個季度，您每季度可獲得13週。 但每個季度有3個月。 13 週無法平均分配到三個月中，所以多出來的那一週會放到其中一個月，如此便能總是維持週數的一致性。 5/4/4表示此季的第一個月有額外的一週。 4/5/4表示多出來的那一週是第二個月，依此類推。在5-4-4行事曆中，第53週會新增到一年的最後一個季度。 </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>：一月有四週，二月有五週，三月有四週，依此類推。 </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>：一月有四週，二月有四週，三月有五週，依此類推。 </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>：一月有五週，二月有五週，三月有四週，依此類推。 </li> 
    </ul> <p>注意：所有Adobe Analytics工具都支援此日曆選項：Analysis Workspace、Report Builder和Activity Map。 唯一例外為 Data Warehouse，它不支援自訂日曆。 </p> </td> 
  </tr> 
 </tbody> 
</table>

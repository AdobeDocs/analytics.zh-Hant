---
description: 描述雜湊碰撞為何及其出現方式。
keywords: Analytics Implementation;hash;collision;prop;evar;hash
title: 雜湊碰撞
topic: Developer and implementation
uuid: 7dfd6e64-4a62-4087-bc28-fb867ec2b1b6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 雜湊碰撞

描述雜湊碰撞為何及其出現方式。

Adobe 會預設將 prop 及 eVar 值視為字串，即便數值為數字亦無不同。有時這些字串長達數百字元，有時則較短。為節省空間、改善效能，並將所有物件維持相同大小，則這些字串不應直接使用於處理中的表格。相反的，每個值都會計算 32 位元或 64 位元的雜湊。所有報表都會執行這些雜湊值，直到資料存在，資料中的每個雜湊則會被原來的文字取代。若不經此壓縮過程，報表須費時數分鐘才能執行。

在多數欄位中，字串內容會先轉換為小寫 (減少獨特值)。數值會每月轉換為雜湊 (數值於每月首次出現時轉換)。每月如此轉換，偶爾也可能將兩個獨特變數值轉換為相同的雜湊值。這種現象稱為&#x200B;*雜湊碰撞*。

雜湊碰撞可於以下情形出現於報表:

* 若您正在追蹤數值的趨勢，且在某月時出現困難，這很可能是因為該變數其他數值雜湊的數值與您在正觀察的數值相同。
* 特定數值的區段也可能發生同樣的情形。

<p class="head"> <b>雜湊碰撞範例</b> </p>

雜湊碰撞發生的可能性會隨維度 (eVar) 中的獨特數值數目增加。例如，當月較晚輸入的數值可能與較早的數值有相同的雜湊值。以下範例將說明此情形如何導致區段結果變更。假設 eVar62 於 2 月 18 日接收「數值 100」。Analytics 會將表格維持為此形式:

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 串數值 </th> 
   <th colname="col2" class="entry"> 雜湊 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 數值 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>數值 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 數值 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

若您建立一個尋找造訪的區段，其中 eVar62=「數值 500」，則 Analytics 會判斷「數值 500」是否含有雜湊。由於「數值 500」並不存在，Analytics 會回報訪客數為 0。之後，在 2 月 23 日，eVar62 接收「數值 500」，其雜湊亦為 123。表格內容如下:

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar62 串數值 </th> 
   <th colname="col2" class="entry"> 雜湊 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 數值 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>數值 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 數值 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>數值 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

相同區段再次執行時，會尋找「數值 500」的雜湊值，結果找到 123，報表便回報雜湊值為 123 的所有造訪。於是，結果也會納入 2 月 18 日的造訪。

此情形可能在使用 Analytics 時造成困擾。Adobe 會持續研究，以減少將來發生此類雜湊碰撞的可能性。要避免此情形，可以設法在變數之間散佈獨特值，處理規則時移除非必要的數值，或減少每個變數的數值數。

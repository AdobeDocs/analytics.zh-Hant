---
description: 顯示瀏覽內每個值引發所在處的平均深度。在判斷您的訪客經過多深入的瀏覽後才進入指定頁面或 prop 值時，這會是很有價值的量度。平均頁面深度可用於任何已啟用路徑的變數。
title: 平均頁面深度
topic: Metrics
uuid: 4d8a3a3c-c698-4210-8dd8-a02a1638483c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 平均頁面深度

顯示瀏覽內每個值引發所在處的平均深度。在判斷您的訪客經過多深入的瀏覽後才進入指定頁面或 prop 值時，這會是很有價值的量度。平均頁面深度可用於任何已啟用路徑的變數。

例如，如果一次瀏覽包含下列路徑: 頁面 A &gt; 頁面 B &gt; 頁面 C &gt; 頁面 D &gt; 頁面 E &gt; 頁面 F，深度便是該頁面所在位置的索引。例如，「頁面 A」的深度為 0，「頁面 F」的深度為 5。平均值會合併所有瀏覽來計算。小於 1 (例如 0.9) 的頁面深度，是在目前頁面之前瀏覽的所有頁面數的平均值。

[!UICONTROL 頁面深度]有助於理解指定頁面在使用者路徑中的通常位置 (不考量該路徑中的前面或後面幾頁)。因此，透過它可確定該頁面在使用者總體網站瀏覽路徑中的合適位置。這項分析資料在[!UICONTROL 頁面]報告上最為直觀。

<table id="table_E92B185A487C40E28C70EA30EDF73A40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> <p>計算頁面事件數與檢視的頁面數除以瀏覽數的值，以顯示頁面的平均點按數。考量相同的瀏覽路徑: </p> <p>A &gt; B &gt; B &gt; C &gt; D &gt; B </p> <p>「計算重複例項」選項啟用時 (Ad Hoc Analysis 預設為開啟、Marketing Reports &amp; Analytics 一律開啟)，會針對每個頁面和頁面事件 (包括重新載入) 計算點按數。在此次瀏覽中，頁面 A 收到的點按數為 0。頁面 B 的點按數則會是 1、2 與 5。平均值的計算方式為 [(1+2+5) / 3]，得出頁面 B 的平均頁面深度為 2.67。 </p> <p>「計算重複例項」選項停用時，頁面 B 會收到 1 和 4。不計算第二個項目。計算式為 [(1+4) / 2 = 2.5]。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 轉換 </td> 
   <td colname="col2"> 不適用 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [頁面深度報告](/help/components/c-variables/dimensionslist/reports-page-depth.md)


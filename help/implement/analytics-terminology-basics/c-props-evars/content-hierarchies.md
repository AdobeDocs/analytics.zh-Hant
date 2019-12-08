---
description: 內容階層的常見用法之一，是顯示訪客從特定頁面、層級等位置所採用的不同路徑。
keywords: Analytics Implementation;content hierachies;hier
title: 計算內容階層數
topic: Developer and implementation
uuid: d41df92d-65fb-44de-bf46-8fac24303dad
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 計算內容階層數

內容階層的常見用法之一，是顯示訪客從特定頁面、層級等位置所採用的不同路徑。

**要如何追蹤我的[!UICONTROL 內容階層]？**

您必須先瞭解追蹤[!UICONTROL 內容階層]的報告需求。若追蹤階層的需求非常瑣碎，一般會建議使用階層 (*`hier`*) 變數。階層通常需要嚴格、預先定義的分類法，在此分類法中，相同的子節點鮮少會從屬於多個父節點下。考量下列範例:

[!UICONTROL 全域階層]

所有網站 &gt; 地區 &gt; 國家 &gt; 語言 &gt; 類別

在此範例中，階層可從語言層級開始劃分。若需求是要報告整體的「英文」流量，您可能會遇到英文出現在美國、英國、澳洲等國家之下的問題。階層可讓您僅執行向下鑽研。若要橫切不同的階層，最理想的方式是使用[!UICONTROL 自訂流量變數] (prop)。

若要讓使用者能夠向下鑽研整個網站 (類似於使用者瀏覽網站的情形)，並且報告階層中每個層級的[!UICONTROL 獨特訪客]，建議您使用階層變數。

在某些情況下同時使用 prop 和&#x200B;*`hier`*&#x200B;變數較為合理。以下是各種變數類型支援的 prop: 

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> Prop </th> 
   <th class="entry"> 階層 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 關聯 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 路徑分析 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 頁面檢視 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 不重複訪客 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> 分類 </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>


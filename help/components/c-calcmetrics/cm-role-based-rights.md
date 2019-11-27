---
description: 管理員級使用者和非管理員之間的計算量度權限不一樣。
title: 計算量度角色型權限
uuid: 7c14d32d-370c-4afa-8f80-5bbd8fc12ec7
translation-type: tm+mt
source-git-commit: 52cc111c0f28b099f038e4b6c69a9431fe506111

---


# 計算量度: 角色型權限

管理員級使用者和非管理員之間的計算量度權限不一樣。

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> 建立 </th> 
   <th colname="col2" class="entry"> 共用 </th> 
   <th colname="col3" class="entry"> 檢視／管理 </th> 
   <th colname="col4" class="entry"> 核准 </th> 
   <th colname="col5" class="entry"> 套用 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>管理員級使用者</b> </td> 
   <td colname="col02"> 管理員可以建立計算量度，也可以建立<a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html"  >群組</a>來限制使用者建立計算量度的權限。 </td> 
   <td colname="col2"> 可以將區段共用給整個公司、使用者群組以及個別使用者。 </td> 
   <td colname="col3"> <span class="keyword">Reports &amp; Analytics</span>: 可以檢視/編輯/刪除...其所擁有的計算量度以及其他使用者的計算量度。 <p> <span class="keyword">Ad Hoc Analysis</span> 和 <span class="keyword">Report Builder</span>: 可以檢視/編輯/刪除...其所擁有的計算量度以及與他共用的計算量度。 </p> </td> 
   <td colname="col4"> 可以核准計算量度做為標準。 </td> 
   <td colname="col5"> 可以在整個組織內套用任何計算量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>非管理員級使用者</b> </td> 
   <td colname="col02"> 依預設，使用者可以建立計算量度。但是，管理員有可能限制這些權限。 </td> 
   <td colname="col2"> 僅可將區段共用給個別使用者 </td> 
   <td colname="col3"> 只可以檢視/編輯/刪除...其所擁有的計算量度。 <p>非管理員使用者必須擁有所有元件事件的存取權，才能查看共用量度 (仍將強制執行管理控制台中的權限)。 </p> <p>如果控制面板或排程報表與非管理員使用者共用，而他們沒有共用量度，則報表會在套用量度時執行（假設他們擁有檢視事件的權限）。 不過，該使用者將無法查看定義或編輯量度。 </p> </td> 
   <td colname="col4"> 僅可取用已核准的計算量度；無法標記為已核准。 </td> 
   <td colname="col5"> 可套用自己所擁有的計算量度和已共用給自己的區段。 </td> 
  </tr> 
 </tbody> 
</table>


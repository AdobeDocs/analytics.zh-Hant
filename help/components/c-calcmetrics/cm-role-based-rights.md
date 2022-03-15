---
description: 管理員級使用者和非管理員之間的計算量度權限不一樣。
title: 計算量度 - 角色型權限
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '251'
ht-degree: 100%

---

# 計算量度：角色型權限

管理員級使用者和非管理員之間的計算量度權限不一樣。

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> 建立 </th> 
   <th colname="col2" class="entry"> 共用 </th> 
   <th colname="col3" class="entry"> 檢視/管理 </th> 
   <th colname="col4" class="entry"> 核准 </th> 
   <th colname="col5" class="entry"> 套用 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>管理員級使用者</b> </td> 
   <td colname="col02"> 管理員可以在 Admin Console 中建立計算量度及產品描述檔，以限制使用者建立計算量度的權限。 </td> 
   <td colname="col2"> 可以與整個公司、使用者群組及個別使用者分享。 </td> 
   <td colname="col3"> <span class="keyword">Reports &amp; Analytics</span>：可以檢視/編輯/刪除...他們自己的以及其他用戶的計算量度。 <p> <span class="keyword"> Report Builder</span>：可檢視/編輯/刪除/等。其所擁有的計算量度以及與其共用的計算量度。 </p> </td> 
   <td colname="col4"> 可以核准計算量度做為標準。 </td> 
   <td colname="col5"> 可以在整個組織內套用任何計算量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>非管理員級使用者</b> </td> 
   <td colname="col02"> 依預設，使用者可以建立計算量度。但是，管理員有可能限制這些權限。 </td> 
   <td colname="col2"> 僅可將區段共用給個別使用者 </td> 
   <td colname="col3"> 只可以檢視/編輯/刪除...其所擁有的計算量度。 <p>非管理員使用者必須擁有所有元件事件的存取權，才能查看共用量度 (仍將強制執行管理控制台中的權限)。 </p> <p>如果與非管理員使用者共用儀表板或計劃報表，但未與他們共用量度，則報表會在套用量度的情形下執行 (假設該使用者具有檢視事件的權限)。不過，該使用者將無法查看定義或編輯量度。 </p> </td> 
   <td colname="col4"> 僅可取用已核准的計算量度；無法標記為已核准。 </td> 
   <td colname="col5"> 可套用自己所擁有的計算量度和已共用給自己的區段。 </td> 
  </tr> 
 </tbody> 
</table>

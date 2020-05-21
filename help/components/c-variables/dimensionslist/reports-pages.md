---
description: 基於接收最多流量的網頁對頁面進行排名。如果您的公司問題涉及到頁面的量化資料，則可使用此報告來新增正確的量度，從而加以解決。
title: 頁面
topic: Reports
uuid: 6435e262-e734-4c15-af5b-173799d5cc43
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 頁面

基於接收最多流量的網頁對頁面進行排名。如果您的公司問題涉及到頁面的量化資料，則可使用此報告來新增正確的量度，從而加以解決。

## 分配、過期和特殊值 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

請注意，在「Reports &amp; Analytics」中，頁面報表上的量度使用線性分配。例如，收入會均分給購買事件前檢視的所有頁面。如此可能會跟某些量度產生混淆，例如購物車新增，您預期只會在單一頁面發生的量度。

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">報表 &amp; <p>Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 量度分配 </td> 
   <td colname="col2"> 線性 </td> 
   <td colname="col3"> 分配是每個維度專屬的。預設為「上次接觸」分配，但 'pagename' 維度是例外情形。如果套用自訂事件至 'pagename'，將是「精確點擊」分配。 </td> 
   <td colname="col4"> <p>相同頁面檢視上設定的值 </p> </td> 
   <td colname="col5"> <p>相同頁面檢視上設定的值 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值過期時間 </td> 
   <td colname="col2"> 頁面檢視 </td> 
   <td colname="col3"> 頁面檢視 </td> 
   <td colname="col4"> 頁面檢視 </td> 
   <td colname="col5"> 頁面檢視 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值限制 </td> 
   <td colname="col2"> <p>每月前 500,000 個獨特值 + 流量的新值 </p> </td> 
   <td colname="col3"> <p>每月前 500,000 個獨特值 + 流量的新值 </p> </td> 
   <td colname="col4"> 無 </td> 
   <td colname="col5"> <p>每月前 500,000 個獨特值 + 流量的新值 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特殊值 </td> 
   <td colname="col2"> <p>(低流量) 代表過去前 500,000 個值尚未收到可以報告的足夠流量。 </p> </td> 
   <td colname="col3"> <p>(低流量) 代表過去前 500,000 個值尚未收到可以報告的足夠流量。 </p> </td> 
   <td colname="col4"> 無 </td> 
   <td colname="col5"> <p>(低流量) 代表過去前 500,000 個值尚未收到可以報告的足夠流量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

在「Reports &amp; Analytics」中，如果您在頁面報表中將任何自訂事件套用為量度，則套用線性分配。

這表示即使該事件是以 s.tl() 呼叫傳送，仍會取得先前 s.t() 呼叫的線性分配。範例：

| 頁面名稱 | Page_event | 事件 |
|---|---|---|
| 頁面 1 | **s.t()** |  |
| 頁面 1 | s.tl() | Event1 |
| 頁面 1 | s.tl() | Event1 |
| 頁面 1 | s.tl() | Event1 |
| 頁面 2 | **s.t()** |  |
| 頁面 2 | **s.t()** |  |
| 頁面 2 | s.tl() | Event1 |

對於這種情況，我們將在頁面報表中取得下列分配：

| 頁面 | 頁面檢視 | 事件 1 |
|---|---|---|
| 頁面 1 | 1 | 1+1+1+1/3 = 3.33 |
| 頁面 2 | 2 | 2/3 = 0.67 |

即使事件是以 s.tl 呼叫傳送，在以 (s.t() call) 傳送的該事件前檢視的頁面仍可取得部分評價。

## 附註 {#section_47B0F4746D4847AC9E8697127063F4D0}

* 若頁面名稱不存在，則會使用 URL。
* 若點擊無頁面名稱、頁面 URL 或事件清單 (無商務事件)，則會排除點擊。
* 頁面上的劃分顯示有持續值的所有頁面。


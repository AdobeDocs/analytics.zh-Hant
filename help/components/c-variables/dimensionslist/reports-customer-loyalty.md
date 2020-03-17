---
description: 「客戶忠誠度」可揭示客戶的購買模式。
title: 客戶忠誠度
topic: Reports
uuid: 7dc30b57-7b18-4228-a6ab-6eb66b3d9402
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 客戶忠誠度

「客戶忠誠度」可揭示客戶的購買模式。

此報表會根據 4 個忠誠度類別來顯示客戶的購買模式：

* 非客戶
* 新客戶
* 回頭客戶
* 忠誠客戶

雖然您可以在此報告中檢視非購買量度 (例如：自訂事件、購物車事件等)，但系統仍會根據下單數量來顯示類別。例如，訪客可將命名為「內部搜尋」的自訂事件新增至報告。[!UICONTROL 回頭客戶]明細項目會顯示先前曾購買兩次的訪客所執行的內部搜尋數量，而非執行過兩次內部搜尋的訪客數量。

**客戶忠誠度處理**

下表定義 Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis 和 Data Warehouse 目前處理客戶忠誠度的方式：

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>2016 年 5 月 19 日之後 </p> </th> 
   <th colname="col3" class="entry"> <p>2016 年 4 月 21 日至 5 月 19 日之間 </p> <p>(不適用 Data Warehouse) </p> </th> 
   <th colname="col4" class="entry"> <p>2016 年 4 月 21 日之前 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>非客戶 </p> </td> 
   <td colname="col2"> <p>從未購買過的訪客 </p> </td> 
   <td colname="col3"> <p>在瀏覽結束時都未進行任何購買的訪客。 </p> </td> 
   <td colname="col4"> <p>無法使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新客戶 </p> </td> 
   <td colname="col2"> <p>購買過一次的訪客 </p> </td> 
   <td colname="col3"> <p>在該瀏覽結束時購買過 1 次的訪客。 </p> <p>(如果發生購買，則客戶狀態是在該購買後的下一次瀏覽時更新。) </p> </td> 
   <td colname="col4"> <p>在該瀏覽結束時都未進行任何購買的訪客。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>回頭客戶 </p> </td> 
   <td colname="col2"> <p>購買過 2 次的訪客 </p> </td> 
   <td colname="col3"> <p>在購買第 2 次的瀏覽結束時購買過 2 次的訪客。 </p> <p>(如果發生購買，則客戶狀態是在該購買後的下一次瀏覽時更新。) </p> </td> 
   <td colname="col4"> <p>在該次購買的瀏覽結束時購買過 1 次的訪客。 </p> <p>(如果發生購買，則客戶狀態是在該購買後的下一次瀏覽時更新。) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>忠誠客戶 </p> </td> 
   <td colname="col2"> <p>購買過 3 次以上的訪客 </p> </td> 
   <td colname="col3"> <p>在最近購買的瀏覽結束時購買過 3 次的訪客。 </p> <p>(如果發生購買，則客戶狀態是在該購買後的下一次瀏覽時更新。) </p> </td> 
   <td colname="col4"> <p>在最近購買的瀏覽結束時購買過 2 次的訪客。 </p> <p>(如果發生購買，則客戶狀態是在該購買後的下一次瀏覽時更新。) </p> </td> 
  </tr> 
 </tbody> 
</table>

| 第 14 版客戶忠誠度 (目前) |
|---|
| 新客戶 | 1 次瀏覽和 1 次購買 |
| 回頭客戶 | 超過 1 次瀏覽和 2 次購買 |
| 忠誠客戶 | 超過 1 次瀏覽和 3 次以上購買 |

忠誠度狀態會隨每次瀏覽時的購買事件而立即變更。例如，新客戶 (購買 1 次) 進行購買，然後在完成購買後、同一次瀏覽裡，進行註冊電子報，則該電子報註冊事件視為「回頭客戶」互動，因為訪客的客戶忠誠度狀態已在購買後立即變更。

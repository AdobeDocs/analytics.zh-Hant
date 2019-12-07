---
description: Adobe 需要事先收到有關新帳戶設定、流量尖峰及流量增加的通知。必須事先配置硬體，方可降低延遲並減少對整體系統的不利影響。
title: 流量增加所需的前置時間
topic: Admin tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 流量增加所需的前置時間

Adobe 需要事先收到有關新帳戶設定、流量尖峰及流量增加的通知。必須事先配置硬體，方可降低延遲並減少對整體系統的不利影響。

配置硬體是由透過 Reports &amp; Analytics 使用者介面提交的警報驅動。

> [!IMPORTANT] Adobe 無法接受「預留位置」流量變更請求。除非另有指示，否則請盡量遵守建議的前置時間，也不要太早傳送警報。請參閱[排程流量尖峰](/help/admin/c-traffic-management/t-traffic-schedule-spike.md)或[指定永久性流量增加](/help/admin/c-traffic-management/t-traffic-permanent.md)。

使用以下準則判斷您必須在多久之前提交流量警報。

## 硬體配置前置時間

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 每日流量估計值 (點擊) </th>
   <th colname="col2" class="entry"> <p>所需的前置時間 (1 月到 10 月) </p> </th>
   <th colname="col3" class="entry"> <p>所需的前置時間 (11 月到 12 月) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 最多 1,000,000 </td>
   <td colname="col2"> 無需前置時間 </td>
   <td colname="col3"> 無需前置時間 </td>
  </tr>
  <tr>
   <td colname="col1"> 1,000,000 - 5,000,000 </td>
   <td colname="col2"> 兩個工作天 </td>
   <td colname="col3" morerows="3"> 11 月與 12 月期間的所有流量增加均須在 9 月 1 日前提交。這是為了在需要因應假期流量的情況下，有充足的時間購買容量。 </td>
  </tr>
  <tr>
   <td colname="col1"> 5,000,000 - 10,000,000 </td>
   <td colname="col2"> 一週 </td>
  </tr>
  <tr>
   <td colname="col1"> 10,000,000 - 25,000,000 </td>
   <td colname="col2"> 兩週 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>超過 25,000,000 </p> </td>
   <td colname="col2"> 一或多個月 </td>
  </tr>
 </tbody>
</table>

其他需要考量的事項包括:

* 如果您啟動數個報表套裝，或是予以新增至多達上方所列的數量，他們適用的前置時間會是每位客戶預期流量的總和。
* 提交流量變更前請準備好以下資訊:

   * 報表套裝 ID
   * 每日預估點擊數
   * 上線日期

* 當流量減少或某報表套裝停用時，也需要使用客戶提醒。

## 因未達成流量而解除配置硬體

如果客戶提醒中的預計流量沒有在「上線日期」後的 4 週內實現，系統將解除配置新帳戶、流量尖峰及流量增加所用的硬體。如果流量仍合乎預期，就必須產生新客戶提醒作為流量增加。

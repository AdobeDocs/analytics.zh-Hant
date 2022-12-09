---
description: Adobe 需要事先收到有關新帳戶設定、流量尖峰及流量增加的通知。必須事先配置硬體，方可降低延遲並減少對整體系統的不利影響。
title: 流量增加所需的前置時間
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 6f7f46b0fee46e572a65f639ea511478c0118f4e
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 78%

---

# 流量增加所需的前置時間

Adobe 需要事先收到有關新帳戶設定、流量尖峰及流量增加的通知。必須事先配置硬體，方可降低延遲並減少對整體系統的不利影響。

配置硬體是由透過 Reports &amp; Analytics 使用者介面提交的警報驅動。

>[!IMPORTANT]
>
>Adobe 無法處理「預留位置」流量變更請求。 除非另有指示，否則請盡量遵守建議的前置時間，也不要太早傳送警報。請參閱[排程流量尖峰](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)或[指定永久性流量增加](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)。

使用以下準則判斷您必須在多久之前提交流量警報。

## 硬體配置前置時間


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 流量變更類型 </th>
   <th colname="col2" class="entry"> 所需的前置時間 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 新帳戶設定 </td>
   <td colname="col2"> <ul><li>3個工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 與過去30天相比，每日流量的平均尖峰或永久性流量突然增加高達25%</td>
   <td colname="col2"> <ul><li>每日點擊數&lt; 100M的報表套裝：不需要通知</li><li>每日點擊數超過1億次的報表套裝：5個工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 與過去30天相比，日均流量的流量尖峰或永久性流量突然增加超過25%</td>
   <td colname="col2"> <ul><li>5個工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 假日活動10月至12月 </td>
   <td colname="col2"> <ul><li>一個日曆月</li></ul> </td>
  </tr>
 </tbody>
</table>

其他需要考量的事項包括：

* 如果您啟動數個報表套裝，或是予以新增至多達上方所列的數量，他們適用的前置時間會是每位客戶預期流量的總和。
* 提交流量變更前請準備好以下資訊：

   * 報表套裝 ID
   * 每日預估點擊數
   * 上線日期

* 當流量減少或某報表套裝停用時，也需要用到客戶提醒。

## 因未達成流量而解除配置硬體

如果客戶提醒中的預計流量沒有在「上線日期」後的 4 週內實現，系統將解除配置新帳戶、流量尖峰及流量增加所用的硬體。如果流量仍合乎預期，就必須產生新客戶提醒作為流量增加。

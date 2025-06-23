---
description: Adobe 需要事先收到有關新帳戶設定、流量尖峰及流量增加的通知。必須事先配置硬體，方可降低延遲並減少對整體系統的不利影響。
title: 流量增加所需的前置時間
feature: Report Suite Settings
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 100%

---

# 流量增加所需的前置時間

Adobe 需要事先收到有關新帳戶設定、流量尖峰及流量增加的通知。必須事先配置硬體，方可降低延遲並減少對整體系統的不利影響。

>[!IMPORTANT]
>
>Adobe 無法處理「預留位置」流量變更請求。 除非另有指示，否則請盡量遵守建議的前置時間，也不要太早傳送警報。

使用以下準則判斷您必須在多久之前提交流量警報。

## 硬體配置前置時間


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 流量變更類型 </th>
   <th colname="col2" class="entry"> 需要前置時間 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 新帳戶設定 </td>
   <td colname="col2"> <ul><li>3 個工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 與過去 30 天相比，平均每日流量的流量尖峰或瞬間永久流量增加最多 25%</td>
   <td colname="col2"> <ul><li>每天點擊次數 &lt; 1 億的報表套裝：無需通知</li><li>每天點擊次數超過 1 億次的報表套裝：5 個工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 與過去 30 天相比，平均每日流量的流量尖峰或瞬間永久流量增加超過 25%</td>
   <td colname="col2"> <ul><li>5 個工作日</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> 10 月至 12 月假期活動 </td>
   <td colname="col2"> <ul><li>一個月 (曆月)</li></ul> </td>
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

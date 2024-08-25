---
description: 由於各種原因，Adobe Analytics 和 Adobe Audience Manager 中的訪客量度有些具有相似的定義，但並非完全一致。
title: 訪客計數差異
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 85%

---

# 訪客計數差異

出於各種原因，Adobe Analytics 和 Adobe Audience Manager 中的訪客量度有些具有相似的定義，但並非完全一致。

訪客量度包括：

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 量度 </th> 
   <th colname="col3" class="entry"> 定義 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=zh-Hant"  > Adobe Audience Manager：總區段母體</a> </p> </td> 
   <td colname="col3"> <p>回顧期間，屬於區段成員的裝置計數 (Experience Cloud ID)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=zh-Hant"  > Adobe Audience Manager：即時區段人口數</a> </p> </td> 
   <td colname="col3"> <p>回顧期間，屬於區段成員且達到所設屬性的裝置計數 (Experience Cloud ID)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：獨特訪客數 </p> </td> 
   <td colname="col3"> <p>在報告視窗中，向您顯示達到所設屬性的獨特訪客人數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：擁有 Experience Cloud ID 的訪客 </p> </td> 
   <td colname="col3"> <p>報告視窗中，向您顯示具有 Experience Cloud ID 且達到所設屬性的訪客人數 (不重複計數)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Adobe Audience Manager即時區段母體與Audience Analytics報表中使用的Experience CloudID為Analytics訪客最相似。 不過近期由於一些因素，兩者之間將會存在著些許差異。貢獻因子包括：

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 因素 </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager：即時區段人口數 </th> 
   <th colname="col3" class="entry"> Analytics：擁有 Experience Cloud ID 的訪客 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>時區 </p> </td> 
   <td colname="col2"> <p>UTC (世界協調時間) </p> </td> 
   <td colname="col3"> <p>依每個報表套裝來指定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂篩選器 </p> </td> 
   <td colname="col2"> <p>否 </p> </td> 
   <td colname="col3"> <p>有，例如 IP 篩選器、機器人篩選器 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>150 個區段上限 </p> </td> 
   <td colname="col2"> <p>否 </p> </td> 
   <td colname="col3"> <p>有，150 個區段整合上限可能會影響 Analytics 計數最高達 5%。若發生截斷情況，「客群名稱」維度中會顯示「已達客群上限」。 </p> </td> 
  </tr> 
 </tbody> 
</table>

請參閱[了解 Analytics 和 Audience Manager 中的區段](/help/integrate/c-audience-analytics/aam-analytics-segments.md)，以取得 Analytics 和 Audience Manager 資料及區段間細微差異的其他說明。

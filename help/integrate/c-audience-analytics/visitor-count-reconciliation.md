---
description: 由於各種原因，Adobe Analytics 和 Adobe Audience Manager 中的訪客量度有些具有相似的定義，但並非完全一致。
title: 訪客計數差異
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 訪客計數差異

由於各種原因，Adobe Analytics 和 Adobe Audience Manager 中的訪客量度有些具有相似的定義，但並非完全一致。

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
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM：總區段人口數</a> </p> </td> 
   <td colname="col3"> <p>回顧期間，屬於區段成員的裝置計數 (Experience Cloud ID)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM：即時區段人口數</a> </p> </td> 
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

Audience Analytics 報表中的 AAM「即時區段人口數」和 Analytics 的「具有 Experience Cloud ID 的訪客數」最為相似。不過近期由於一些因素，兩者之間將會存在著些許差異。貢獻因子包括：

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 因素 </th> 
   <th colname="col2" class="entry"> AAM：即時區段人口數 </th> 
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
   <td colname="col2"> <p>無 </p> </td> 
   <td colname="col3"> <p>有，例如 IP 篩選器、機器人篩選器 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>150 個區段上限 </p> </td> 
   <td colname="col2"> <p>無 </p> </td> 
   <td colname="col3"> <p>有，150 個區段整合上限可能會影響 Analytics 計數最高達 5%。若發生截斷情況，「對象名稱」維度中會顯示「已達對象上限」。 </p> </td> 
  </tr> 
 </tbody> 
</table>

請參閱[了解 Analytics 和 Audience Manager 中的區段](/help/integrate/c-audience-analytics/aam-analytics-segments.md)，以取得 Analytics 和 Audience Manager 資料及區段間細微差異的其他說明。

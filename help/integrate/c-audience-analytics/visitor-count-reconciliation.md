---
description: 由於各種原因，Adobe Analytics 和 Adobe Audience Manager 中的訪客量度有些具有相似的定義，但並非完全一致。
title: 訪客計數差異
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
TQID: https://experienceleague.adobe.com/ksfYYDZ6G9vH7WEZVh-JsN93Rl-jsZTe9-CQADSwnfI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 51%

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
   <td colname="col3"> <p>在回顧期間，屬於區段成員並到達您屬性的裝置計數(Experience Cloud ID)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：獨特訪客數 </p> </td> 
   <td colname="col3"> <p>顯示在報告期間到達您屬性的不重複訪客數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：擁有 Experience Cloud ID 的訪客 </p> </td> 
   <td colname="col3"> <p>顯示有Experience Cloud ID的不重複訪客在報表時段內到達您屬性的數量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Adobe Audience Manager即時區段母體與在Audience Analytics報表中使用的Experience Cloud ID為Analytics的訪客將最相似。 然而，就近期而言，由於多種因素，兩者之間將略有差異。 貢獻因子包括：

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
   <td colname="col2"> <p>UTC （國際標準時間） </p> </td> 
   <td colname="col3"> <p>依報表套裝指定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂篩選器 </p> </td> 
   <td colname="col2"> <p>否 </p> </td> 
   <td colname="col3"> <p>是，例如IP篩選器、機器人篩選器 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>150個區段限制 </p> </td> 
   <td colname="col2"> <p>否 </p> </td> 
   <td colname="col3"> <p>是 — 150區段整合限制最多可影響5%的Analytics計數。 若發生截斷情況，「客群名稱」維度中會顯示「已達客群上限」。 </p> </td> 
  </tr> 
 </tbody> 
</table>

請參閱[了解 Analytics 和 Audience Manager 中的區段](/help/integrate/c-audience-analytics/aam-analytics-segments.md)，以取得 Analytics 和 Audience Manager 資料及區段間細微差異的其他說明。

---
description: 瞭解為何在「區段產生器」中建立的所有區段並非都與Data Warehouse相容。 瞭解支援哪些函式。
title: Data Warehouse 區段相容性
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 56%

---

# Data Warehouse 區段相容性

並非所有在「區段產生器」中建立的區段都與[!DNL Data Warehouse]相容。 下表列出支援的功能。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace、Reports &amp; Analytics </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>排除容器</b> </td> 
   <td> 任何層級皆支援 </td> 
   <td> 僅在頂層的特殊情況下才支援 </td> 
  </tr> 
  <tr> 
   <td> <b>循序區段</b> </td> 
   <td> 支援 </td> 
   <td> 不支援 </td> 
  </tr> 
  <tr> 
   <td> <b>AND和OR可以合併而不受限制</b> </td> 
   <td> 支援 </td> 
   <td> 部分限制。 請參閱下表中的*附註*。 </td> 
  </tr> 
  <tr> 
   <td> <b>巢狀容器</b> </td> 
   <td> 支援 </td> 
   <td> 有些限制（範圍必須縮小，例如訪客可以包含點選，反之則不然） </td> 
  </tr> 
  <tr> 
   <td> <b>維度</b> </td> 
   <td>將維度拖放至區段產生器的<span class="uicontrol">定義</span>欄位，來瞭解其產品相容性。 例如，只有 Analysis Workspace、Reports＆Analytics 支援這些維度： 
    <ul> 
     <li>進入伺服器 </li> 
     <li>專案類別 </li> 
     <li>輸入日期 </li> 
     <li>所有搜尋頁面排名 </li> 
    </ul> </td> 
   <td> 將維度拖放至區段產生器的<span class="uicontrol">定義</span>欄位，來瞭解其產品相容性。 例如，以下維度僅在「Data Warehouse」中才受支援： 
    <ul> 
     <li>IP 位址 </li> 
     <li>頁面 URL </li> 
     <li>訪客 ID </li> 
     <li>Experience Cloud 訪客 ID </li> 
    </ul> <p>下列維度<b>無法</b>在 Data Warehouse 區段中使用： </p> 
    <ul> 
     <li>所有搜尋頁面排名 </li> 
     <li>上午/下午 </li> 
     <li>當月日期 </li> 
     <li>星期 </li> 
     <li>年中的日 </li> 
     <li>進入業務單位 </li> 
     <li>登入（除「登入頁面」外以「登入」開頭的所有維度） </li> 
     <li>退出（除「退出連結」和「退出頁面」以外的所有以「退出」開頭的維度） </li> 
     <li>階層（所有以階層開頭的維度） </li> 
     <li>點擊深度 </li> 
     <li>點擊類型 </li> 
     <li>小時日 </li> 
     <li>月份 </li> 
     <li>找不到頁面 </li> 
     <li>付費搜尋 </li> 
     <li>季別 </li> 
     <li>回訪頻率 </li> 
     <li>單頁造訪次數 </li> 
     <li>事件之前時間 </li> 
     <li>頁面逗留時間 - 分段 </li> 
     <li>每次瀏覽逗留時間 - 分段 </li> 
     <li>追蹤選擇退出原因 </li> 
     <li>美國各州 </li> 
     <li>平日/週末 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>區段堆疊</b> </td> 
   <td> 支援 </td> 
   <td> 支援 </td> 
  </tr>
  <tr>
    <td><b>「等於任何」和「不等於任何」運算子</b></td>
    <td>支援</td>
    <td>不支援</td>
  </tr>
 </tbody> 
</table>

*注意：使用 `AND/OR` 時，Data Warehouse 不支援所有使用 `exclusion` 或 `without` 容器的情況。 如果使用上述組合，Data Warehouse 只支援可重新寫入為 `A AND NOT B` (或&#x200B;**包含此特徵**&#x200B;和&#x200B;**排除此特徵**) 的區段。*

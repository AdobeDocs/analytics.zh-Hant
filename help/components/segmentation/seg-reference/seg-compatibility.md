---
description: 並非所有在「區段產生器」中建立的區段都與Data Warehouse相容。 下表列出支援的功能。
title: Data Warehouse 區段相容性
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 82%

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
   <td> 任何層級均支援 </td> 
   <td> 僅在特殊情況於頂層支援 </td> 
  </tr> 
  <tr> 
   <td> <b>循序區段</b> </td> 
   <td> 支援 </td> 
   <td> 不支援 </td> 
  </tr> 
  <tr> 
   <td> <b>AND 和 OR 可無限結合</b> </td> 
   <td> 支援 </td> 
   <td> 部分限制。請參閱下表中的*附註*。 </td> 
  </tr> 
  <tr> 
   <td> <b>巢狀內嵌的容器</b> </td> 
   <td> 支援 </td> 
   <td> 部分限制 (必須減少範圍，例如訪客可包含點擊，但反向則不適用) </td> 
  </tr> 
  <tr> 
   <td> <b>維度</b> </td> 
   <td>將維度拖放至區段產生器的<span class="uicontrol">定義</span>欄位，來瞭解其產品相容性。 例如，只有 Analysis Workspace、Reports＆Analytics 支援這些維度： 
    <ul> 
     <li>進入伺服器 </li> 
     <li>進入類別 </li> 
     <li>進入日期 </li> 
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
     <li>登入業務單位 </li> 
     <li>登入 (以登入開頭的所有維度，登入頁面除外) </li> 
     <li>退出 (以退出開頭的所有維度，退出連結和退出頁面除外) </li> 
     <li>階層 (以階層開頭的所有維度) </li> 
     <li>點擊深度 </li> 
     <li>點擊類型 </li> 
     <li>小時 </li> 
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

*注意：使用 `AND/OR` 時，Data Warehouse 不支援所有使用 `exclusion` 或 `without` 容器的情況。如果使用上述組合，Data Warehouse 只支援可重新寫入為 `A AND NOT B` (或&#x200B;**包含此特徵**和&#x200B;**排除此特徵**) 的區段。*

---
description: 下表列出查詢參數，這些參數包含每個傳送給資料收集之分析變數的值。
keywords: Analytics Implementation
title: 資料彙集查詢參數
topic: Developer and implementation
uuid: 4d5af486-df27-42fe-bb9c-28938dddf2b2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料彙集查詢參數

下表列出查詢參數，這些參數包含每個傳送給資料收集之分析變數的值。

這項資訊可用於使用[封包分析器](/help/implement/impl-testing/packet-monitor.md)進行偵錯時、手動建立影像要求時，以及使用[動態變數](/help/implement/js-implementation/c-variables/dynvars-overview.md)時。

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> 參數 </th> 
   <th class="entry"> Analytics 變數 </th> 
   <th class="entry"> 填入報表 </th> 
   <th class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> 無 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> 觀眾管理員位置提示 (用於 Experience Cloud 共用設定檔整合) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> 無 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> 觀眾管理員 Blob (用於 Experience Cloud 共用設定檔整合) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輔助 </td> 
   <td colname="col2"> 無 </td> 
   <td colname="col3"> 無 </td> 
   <td colname="col4"> Analytics 訪客 ID </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 表示影像請求的起始處。 </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> 無 </td> 
   <td> 無 </td> 
   <td> 表示影像請求的結束處，意指請求並未被裁截。 </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 瀏覽器高度 </td> 
   <td> 瀏覽器視窗高度 (像素) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 瀏覽器寬度 </td> 
   <td> 瀏覽器視窗寬度 (像素) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> 無 </td> 
   <td> 訪客資料 | 技術 | 監視器色彩深度 </td> 
   <td> 色彩品質 (位元） </td> 
  </tr> 
  <tr> 
   <td> </td><td><p></p></td><td><p></p></td><td><p></p><p><code> &lt;my.a&gt;red&lt;/my.a&gt; </code></p><p></p><p><code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code></p><p><code> my.a = red </code></p><p><code> c.&my.a=red </code></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td><code> D </code></td><td></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p><code> t </code></p><code>
      dd/mm/yyyy&amp;nbsp;hh:mm:ss&amp;nbsp;D&amp;nbsp;OFFSET 
    </code><p><code> 0-6 </code><code> OFFSET </code></p><code>
      offset&amp;nbsp;from&amp;nbsp;GMT&amp;nbsp;in&amp;nbsp;hours&amp;nbsp;*&amp;nbsp;60&amp;nbsp;*&amp;nbsp;-&amp;nbsp;1 
    </code><p></p><code>
      23/09/2016&amp;nbsp;14:00:00&amp;nbsp;1&amp;nbsp;420 
    </code></td></tr><tr><td><code> ts </code></td><td><p></p></td><td></td><td><p></p></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td><p></p></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td><p></p></td></tr></tbody></table>


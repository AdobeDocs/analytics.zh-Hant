---
description: 在設定摘要時，有幾項設定能決定工作的處理方式。
keywords: 資料饋送；工作；設定；每日；每小時；回填每小時資料饋送的資料；回填
seo-description: 在設定摘要時，有幾項設定能決定工作的處理方式。
seo-title: 工作設定
solution: Analytics
title: 工作設定
uuid: e124b4f1-0168-4ea-8657-19207b2f263f
translation-type: tm+mt
source-git-commit: b6169d2febded32d772f82d5917b1132695ab442

---


# 工作設定

設定動態消息時，有些設定會決定工作的處理頻率。

請使用以下設定來配置工作處理時間。這些設定乃是在摘要層級配置，而非工作層級。

<table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 每日 </td> 
   <td colname="col2"> <p>每天的資料會以一個壓縮檔提交。這個檔案的大小上限為 2GB。如果檔案大於 2GB 的未壓縮資料，系統會建立額外的檔案。您每天會收到一次包含所有檔案的提交內容。 </p> <p>每個檔案的命名格式如下: </p> <p> <span class="filepath"><span class="varname"> reportsuite-</span><span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每小時 (預設值) </td> 
   <td colname="col2"> <p>每小時的資料以包含該小時所有資料的單一壓縮檔案進行傳送。您每天會收到 24 次傳送，每個檔案在該小時資料進行處理後傳送。 </p> <p>「每小時」一詞說明的是每筆資料匯出中所傳送的資料時間段，而不是提供傳送的時間段。我們會盡一切所能地處理並傳送每小時資料饋送。 </p> <p>對於每小時資料摘要，預期是 95% 的時間可在該小時有價值資料關閉後 12 小時內傳送摘要。高流量之報表套裝的資料摘要可能需要較長的時間來處理及提交。 </p> <p>接收每小時資料饋送不同於接收多個檔案傳送的每日饋送。接收每小時資料饋送時，每天的資料將根據該小時收集到的資料而分割為 24 個檔案，每個檔案一旦可用時馬上傳送。以多個檔案傳送的每日饋送則是在前一天的資料處理完畢後每天傳送一次，且根據收集到的資料量，分割為 2GB 的遞增檔案。 </p> <p>每個檔案的命名格式如下: </p> <p> <span class="filepath"><span class="varname"> reportsuite-</span><span class="varname"> date-</span><span class="varname"> hour</span>.tar</span> </p> <p>如需影響每小時摘要之因子的詳細資訊，請參閱<a href="../../../export/analytics-data-feed/c-df-contents/jobs-faq.md#concept_7C67A012CCF64B0C8DA33E5A6CF7FD9E" format="dita" scope="local">工作常見問題集</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回填每小時資料饋送的資料 </td> 
   <td colname="col2"> <p>如果您設定新的每小時資料饋送並要求較早日期的資料，超過 60 天前日期的資料可能會以每日格式傳送，而非每小時格式。 </p> <p>在這種情況下，您不會收到那些日期的 24 份單獨傳送，而是會收到含有午夜時間戳記的單份傳送，內含當天的所有資料。如果您要求此類型回填，請確定您的 ETL 已設定為以每日傳送處理。 </p> </td> 
  </tr> 
 </tbody> 
</table>


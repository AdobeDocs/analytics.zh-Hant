---
description: 查閱表格以根據 page_event 值來判斷點擊的類型。
keywords: 資料饋送；頁面；event；page_ event；post_ page_ event
seo-description: 查閱表格以根據 page_event 值來判斷點擊的類型。
seo-title: 頁面事件查閱
solution: Analytics
title: 頁面事件查閱
topic: Reports & Analytics
uuid: 73af597c-5560-466e-94b2-dd1 d6479 c8
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 頁面事件查閱

查閱表格以根據 page_event 值來判斷點擊的類型。

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 點擊類型 </th> 
   <th colname="col02" class="entry"> page_event 值 </th> 
   <th colname="col2" class="entry"> post_page_event 值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 頁面檢視 </td> 
   <td colname="col02"> 與帖子相同 </td> 
   <td colname="col2"> <p>0: 所有頁面檢視 (<code>s.t()</code> 呼叫) </p> <p>0: 來自行動 SDK 的 <code>trackState</code> 呼叫。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 連結追蹤 </td> 
   <td colname="col02"> <p>10: 「其他連結」 </p> <p>10: 來自行動 SDK 的 <code>trackAction</code> 和生命週期呼叫。 </p> <p>11: 「下載連結」 </p> <p>12: 「外部或退出連結」 </p> </td> 
   <td colname="col2"> <p>100: 「其他連結」 </p> <p>100: 來自行動 SDK 的 <code>trackAction</code> 和生命週期呼叫。 </p> <p>101: 「下載連結」 </p> <p>102: 「外部或退出連結」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 里程碑影片 </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 – 媒體開始事件 </p> <p>32 - 僅限媒體更新事件(不執行任何eVar或任何其他變數處理) </p> <p>33 – 媒體 + 其他變數更新事件 (包括 eVar 和其他變數處理) </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 – 媒體開始事件 </p> <p>77 – 僅媒體更新事件 (不執行任何 eVar 或任何其他變數處理) </p> <p>78 – 媒體 + 其他變數更新事件 (包括 eVar 和其他變數處理) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>心率影片 </p> </td> 
   <td colname="col02"> 與帖子相同 </td> 
   <td colname="col2"> <p> 50 = (非黃金時段) 媒體串流開始 </p> <p> 50 = (非黃金時段) 媒體串流關閉 (完成/結束) </p> <p> 52 = (非黃金時段) 媒體串流清除 </p> <p> 53 = (非黃金時段) 媒體串流保持運作 </p> <p> 54 = (非黃金時段) 媒體串流廣告開始 </p> <p> 50 = (非黃金時段) 媒體串流廣告關閉 (完成/結束) </p> <p> 56 = (非黃金時段) 媒體串流廣告清除 </p> <p> 60 = 黃金時段媒體串流開始 </p> <p> 61 = 黃金時段媒體串流關閉 (完成/結束) </p> <p> 62 = 黃金時段媒體串流清除 </p> <p> 63 = 黃金時段媒體串流保持運作 </p> <p> 64 = 黃金時段媒體串流廣告開始 </p> <p> 65 = 黃金時段媒體串流廣告關閉 (完成/結束) </p> <p> 66 = 黃金時段媒體串流廣告清除 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 調查 </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 目標分析 </td> 
   <td colname="col02"> 70 - 代表包含目標活動資料的點擊。70 代表與分析調用有關和無關的點擊。 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>


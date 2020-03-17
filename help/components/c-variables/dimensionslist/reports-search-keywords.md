---
description: 顯示搜尋關鍵字的劃分。
title: 搜尋關鍵字
topic: Reports
uuid: db9d477b-b711-4b93-9c25-3aebe5f2ace6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 搜尋關鍵字

顯示搜尋關鍵字的劃分。

**搜尋關鍵字 - 全部**：顯示用於尋找您網站的每個搜尋關鍵字的劃分資訊。您可以透過按一下清單上面的欄標題，依頁面檢視次數或搜尋關鍵字對此清單進行排序。按一下每個搜尋關鍵字旁邊的放大鏡，檢視網站的搜尋結果。

**搜尋關鍵字 - 付費**：顯示用於尋找您網站的每個付費搜尋關鍵字的劃分資訊。您可以透過按一下清單上面的欄標題，依頁面檢視次數或搜尋關鍵字對此清單進行排序。按一下每個搜尋關鍵字旁邊的放大鏡，檢視網站的搜尋結果。

**搜尋關鍵字 - 免費**：顯示用於尋找您網站的每個免費搜尋關鍵字的劃分資訊。您可以透過按一下清單上面的欄標題，依頁面檢視次數或搜尋關鍵字對此清單進行排序。按一下每個搜尋關鍵字旁邊的放大鏡，檢視網站的搜尋結果。

>[!IMPORTANT]
>
>針對付費和免費搜尋，搜尋引擎在大多數情況下已停止提供搜尋關鍵字作為反向連結的一部分。因此，Adobe 一律將 Google (或 Bing、Yahoo) 網域分類為搜尋。根據反向連結的格式和內容 (即使沒有關鍵字)，Adobe 通常可以確定這是搜尋結果，因此該搜尋將按照「關鍵字無法使用」計數。[更多...](https://helpx.adobe.com/tw/analytics/kb/keyword-unavailable.html)

## 分配、過期和特殊值 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 量度分配 </td> 
   <td colname="col2"> <p>原始值 (預設) </p> <p> 可以變更為線性。 </p> </td> 
   <td colname="col3"> 最近 (可使用量度的線性版本變更為線性) </td> 
   <td colname="col4"> <p>原始值 (預設) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值過期時間 </td> 
   <td colname="col2"> 瀏覽 - 可以縮短但不能加長 </td> 
   <td colname="col3"> 瀏覽 </td> 
   <td colname="col4"> 瀏覽 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值限制 </td> 
   <td colname="col2"> 無限制 (未來版本可能有所變動) </td> 
   <td colname="col3"> 無限制 (未來版本可能有所變動) </td> 
   <td colname="col4"> 無 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特殊值 </td> 
   <td colname="col2"> <p>「無」：瀏覽期間沒有關鍵字的全網站總計。 </p> 「關鍵字無法使用」是關鍵字已從搜尋移除且未傳送至資料收集的搜尋項目。通常發生於客戶登入 Google 帳戶時。適用於付費和免費搜尋。 </td> 
   <td colname="col3"> (低流量) 代表過去前 500,000 個值尚未收到可以報告的足夠流量。 </td> 
   <td colname="col4"> <p> 空白 - 等於「無」，瀏覽期間沒有關鍵字的全網站總計。 </p> <p>「關鍵字無法使用」是關鍵字已從搜尋移除且未傳送至資料收集的搜尋項目。通常發生於客戶登入 Google 帳戶時。適用於付費和免費搜尋。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 報告歷史記錄{#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| 日期 | 變更 |
|---|---|
| 2014 年 1 月 16 日 | Data Warehouse 已更新為符合 Marketing Reports &amp; Analytics 使用的邏輯。在此日期前，搜尋關鍵字不會持續存在於瀏覽期間。 |


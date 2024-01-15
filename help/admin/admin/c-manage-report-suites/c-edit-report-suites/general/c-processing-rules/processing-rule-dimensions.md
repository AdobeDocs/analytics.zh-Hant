---
description: 您可使用處理規則讀取和寫入 (除非另有說明) 的維度。
subtopic: Processing rules
title: 可用於處理規則的維度
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 100%

---

# 可用於處理規則的維度

您可使用處理規則讀取和寫入 (除非另有說明) 的維度。

## 自訂值和內容資料 {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 值 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>自訂值 </p> </td> 
   <td colname="col2"> <p>直接輸入至處理規則之動作的自訂文字或值。這些值可用於後續條件和規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>串連值 </p> </td> 
   <td colname="col2"> <p>結合兩個值而建立的值。例如，可以結合類別和頁面名稱來建立一個子類別。這些值可用於後續條件和規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已修改的值 </p> </td> 
   <td colname="col2"> <p>如果使用處理規則變更了變數值，已變更的值將用於後續條件和規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>內容資料變數 </p> </td> 
   <td colname="col2"> <p>伴隨點擊而傳送的具名變數。 </p> <p>注意：內容資料變數中包含的任何資料都必須複製至報表變數，才會在報表中顯示。內容資料變數無法在任何報告介面中檢視，包括 ClickStream 資料饋送。 </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md">複製內容資料變數至 eVar</a> </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md">使用內容資料變數設定事件</a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md"> 內容資料變數</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 流量變數 {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>階層 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網站區段 </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器 </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 點擊屬性 {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 屬性 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>報表套裝 ID (唯讀) </p> </td> 
   <td colname="col2"> <p>處理規則據以執行的報表套裝，可能不是 AppMeasurement 中指定的原始報表套裝。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面名稱 </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>注意：連結追蹤呼叫在到達處理規則之前會移除 <code>pageName</code> 變數。 如果您使用處理規則重新插入頁面名稱值，則點擊會被視為頁面檢視，而不是連結追蹤呼叫。 Adobe 建議您詳加檢查，確保頁面名稱已設定妥當，然後再修改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面 URL </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> 或目前頁面 URL (若未指定 <code> s.pageURL</code>)。 <p>注意：連結追蹤呼叫在到達處理規則之前會移除 <code>pageURL</code> 變數。 如果您使用處理規則重新插入頁面 URL 值，則點擊會被視為頁面檢視，而不是連結追蹤呼叫。 Adobe 建議您詳加檢查，確保頁面 URL 已設定妥當，然後再修改。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查詢字串參數 </p> </td> 
   <td colname="col2"> <p>目前 URL 中指定之查詢字串參數的值，或為空 (如果沒有參數)。URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b> 中，查詢字串參數 <span class="syntax codeph">cid</span> 的值為 <b>ad1</b>，而查詢字串參數 <span class="syntax codeph">node</span> 的值為 <b>4</b>。 </p> <p>如果您執行的是 JavaScript AppMeasurement H.25.2 或更早的版本，頁面 URL 可能會在 255 個字元之後截斷。JavaScript AppMeasurement H.25.3 (2013 年 1 月發佈) 和更新的版本提供處理規則的完整 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面路徑 </p> </td> 
   <td colname="col2"> <p>頁面 URL 的路徑。URL <b>https://www.example.com/news/a.html?cid=ad1</b> 的路徑是 <span class="syntax codeph">news/a.html</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面網域 </p> </td> 
   <td colname="col2"> <p>URL 中指定的完整主機名稱。https://<span class="syntax codeph">en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面根網域 </p> </td> 
   <td colname="col2"> <p>頁面之主機名稱的最後兩個區段。https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面查詢字串 </p> </td> 
   <td colname="col2"> <p>URL 的完整查詢字串。https://en.main.example.co.uk/index.jsp? <span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結* (唯讀) </p> </td> 
   <td colname="col2"> <p>HTTP 反向連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結查詢字串參數 (唯讀) </p> </td> 
   <td colname="col2"> <p>反向連結 URL 中指定之查詢字串參數的值，或為空 (如果沒有參數)。URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b> 中，查詢字串參數 <span class="syntax codeph">cid</span> 的值為 <b>ad1</b>，而查詢字串參數 <span class="syntax codeph">node</span> 的值為 <b>4</b>。 </p> <p>如果您執行的是 JavaScript AppMeasurement H.25.2 或更早的版本，頁面 URL 可能會在 255 個字元之後截斷。JavaScript AppMeasurement H.25.3 (2013 年 1 月發佈) 和更新的版本提供處理規則的完整 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結網域 (唯讀) </p> </td> 
   <td colname="col2"> <p>反向連結的完整主機名稱。https://<span class="syntax codeph">en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結根網域 (唯讀) </p> </td> 
   <td colname="col2"> <p>反向連結之主機名稱的最後兩個區段。https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結查詢字串 (唯讀) </p> </td> 
   <td colname="col2"> <p>反向連結 URL 中包含的查詢字串參數。https://en.main.example.co.uk/index.jsp? <span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP 位址 (唯讀) </p> </td> 
   <td colname="col2"> <p>瀏覽器所報告的 IP 位址。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者代理 (唯讀) </p> </td> 
   <td colname="col2"> <p>瀏覽器所報告的使用者代理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AppMeasurement 代碼版本 (唯讀) </p> </td> 
   <td colname="col2"> <p>用來進行請求的 appMeasurement 庫版本。使用影像信標時，可以用採用處理規則讀取的自訂值來填入。這個值會出現在 URL 中的下列位置： </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## 轉換變數 {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code> evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行銷活動追蹤代碼 </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>貨幣代碼 </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>清單變數 1-3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> - <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>購買 ID </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>交易 ID </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪客所在州 </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>訪客郵遞區號 </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 成功事件 {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

處理規則可以設定事件但無法將其讀取作為條件。

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>事件 1-1000 </p> <p>(針對 SiteCatalyst 15 客戶，事件 1-100。) </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>purchase、scView、scAdd 和其他購物車事件 </p> </td> 
   <td colname="col2"> <p>預先定義的事件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

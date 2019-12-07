---
description: 「排程任務管理員」的欄位說明。
title: 排程任務管理員
topic: Report builder
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 排程任務管理員

「排程任務管理員」的欄位說明。

「排程任務管理員」可讓您查看現有排程報表的清單，以及其收件者、排程詳細資料及檔案格式。還可讓您重新啟用原本無法執行的排程活頁簿。

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>「排程報表」</b>索引標籤 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報告名稱 </p> </td> 
   <td colname="col2"> <p>指出排程任務的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 電子郵件/FTP </p> </td> 
   <td colname="col2"> <p>收件者的電子郵件或 FTP 位址。 </p> <p>注意: 如果選取電子郵件，大於 1 MB 的報表會自動以 .zip 檔案的形式附加至電子郵件。此功能可讓附件檔案維持在較小的大小，而且無法停用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>發佈選項 </p> </td> 
   <td colname="col2"> <p>如果選取其中一個<a href="/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md"  >Power BI 發佈選項</a>，此欄將會列出 Power BI。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排程 </p> </td> 
   <td colname="col2"> <p>排程的傳送類型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 檔案格式 </p> </td> 
   <td colname="col2"> <p> 報表的傳送格式，如 Excel、PDF、HTML 等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新啟用 </p> </td> 
   <td colname="col2"> <p>當排程活頁簿無法執行時，Report Builder 會嘗試每十五分鐘再執行活頁簿兩次。在第三次嘗試失敗後，Report Builder 會停用排程並顯示<span class="wintitle">「重新啟用」</span>按鈕。當您重新啟用活頁簿時，排程的傳送會從成為停用狀態的時間重新啟動。 </p> <p>例如，如果排程的活頁簿在 14 天前停用而您在今天將其重新啟用，它會執行遺漏的每個天數，因此會傳送 14 次。如果您不想要傳送遺漏活頁簿的天數，可以刪除排程活頁簿，然後再使用相同的排程參數建立新的排程活頁簿。 </p> <p> <p>附註: 在瞭解系統停用活頁簿的原因之前，請避免重新啟用活頁簿。其中一個疑難排解的方法是下載停用的活頁簿，然後在用戶端重新整理。如果您未發現任何錯誤，應該就可以重新啟用活頁簿。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最後傳送 </p> </td> 
   <td colname="col2"> <p>最後一次傳送報表的日期與時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>「收件者」</b>索引標籤 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>收件者電子郵件 </p> </td> 
   <td colname="col2"> 報表的電子郵件收件者。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報表 </p> </td> 
   <td colname="col2"> 傳送給每位收件者的報表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>「報表歷史記錄」</b>索引標籤 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案名稱 </p> </td> 
   <td colname="col2"> 指出排程任務的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期 </p> </td> 
   <td colname="col2"> 最後一次傳送報表的日期與時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>狀態 </p> </td> 
   <td colname="col2"> 狀態表示報表是否「已傳送」或「未傳送」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>電子郵件/FTP </p> </td> 
   <td colname="col2"> 報表收件者的電子郵件或 FTP 位址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案格式 </p> </td> 
   <td colname="col2"> 報表的傳送格式，如 Excel、PDF、HTML 等。 </td> 
  </tr> 
 </tbody> 
</table>

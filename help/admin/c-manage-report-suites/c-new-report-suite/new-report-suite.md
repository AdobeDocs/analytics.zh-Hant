---
description: 您可以選取預先定義的範本，或使用其中一個現有的報表套裝作為模型，來建立新的報表套裝。
title: 新的報表套裝 - 設定
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 新的報表套裝 - 設定

您可以選取預先定義的範本，或使用其中一個現有的報表套裝作為模型，來建立新的報表套裝。

建立報表套裝時[所使用元素的說明](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)。

> [!NOTE]附註: [虛擬報表套裝文件](/help/components/vrs/c-workflow-vrs/vrs-create.md)會示範如何建立虛擬報表套裝。

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 報表套裝 ID </span> </td> 
   <td colname="col2"> <p>指定僅能含英數字元的不重複 ID。此 ID 在建立後即無法變更。由 Adobe 設定必要的 ID 首碼，此值無法變更。 </p> <p>在建立多個報表套裝時，請確定您所使用的命名慣例可確保唯一報表套裝 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 網站標題</span> </td> 
   <td colname="col2">在「<span class="wintitle">管理工具</span>」中識別報表套裝。此標題也會用於套裝標題的<span class="wintitle">報表套裝</span>下拉式清單中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 時區</span> </td> 
   <td colname="col2"> 排程事件與時間戳記資料。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基礎 URL</span> </td> 
   <td colname="col2"> (可選) 定義報表套裝的基本網域。如果您未明確定義報表套裝的內部 URL 篩選器，此 URL 就會當做內部 URL 篩選器使用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 預設頁面</span> </td> 
   <td colname="col2"> <p>(可選) 從遇到的 URL 中移除<span class="wintitle">預設頁面</span>值的發生次數。若您的<span class="wintitle">人氣最高的頁面</span>報表包含 URL 而非頁面名稱，此設定可防止同一網頁出現多個 URL。 </p> <p>例如，URL <span class="filepath">https://mysite.com</span> 和 <span class="filepath">https://mysite.com/index.html</span> 通常是同一頁面。您可移除無關的檔案名稱，以便讓上述兩個 URL 在報表中均顯示為 <span class="filepath">https://mysite.com</span>。 </p> <p>若您未設定此值，則 Analytics 會從 URL 中自動移除下列檔案名稱: <span class="filepath">index.htm</span>、<span class="filepath">index.html</span>、<span class="filepath">index.cgi</span>、<span class="filepath">index.asp</span>、<span class="filepath">default.htm</span>、<span class="filepath">default.html</span>、<span class="filepath">default.cgi</span>、<span class="filepath">default.asp</span>、<span class="filepath">home.htm</span>、<span class="filepath">home.html</span>、<span class="filepath">home.cgi</span> 與 <span class="filepath">home.asp</span>。 </p> <p>若要停用檔案名稱移除，請指定一個 URL 中永遠不會出現的「預設頁面」值， </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上線日期 </p> </td> 
   <td colname="col2">通知 Adobe 您要讓此報表套裝開始生效的日期。如果您的部署計劃變更，請使用<a href="/help/admin/c-traffic-management/traffic-management.md">「流量管理」</a>下的<span class="wintitle">「永久性預期流量」</span>工具，提供更新的流量估計值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 預計的每日頁面檢視次數</span> </td> 
   <td colname="col2"> 識別您預期此報表套裝在一天內可支援的頁面檢視預估次數。大流量將需要更長的批準過程。若想避免處理延遲，此項估計請盡量準確。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 基本貨幣</span> </td> 
   <td colname="col2"> <p>指定用來儲存所有貨幣資料的預設貨幣。Analytics 報告會使用它收到資料時的轉換率，將其他貨幣的交易換算為基本貨幣。 </p> <p> Analytics 報告會使用<span class="varname"> currencyCode</span> 這個 JavaScript 變數來識別指定交易的貨幣。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">停用多位元組字元支援</span> </td> 
   <td colname="col2"> <p>停用報表套裝的多位元組字元支援。若您停用多位元組字元支援，系統會假設資料採用 ISO-8859-1 格式。網頁必須在<span class="varname"> charSet</span> 這個 JavaScript 變數中指定字元集。 </p> <p>多位元組字元支援可使用 UTF-8 儲存報表套裝中的字元。系統收到報告時就會將您網頁資料的字元集轉換為 UTF-8 字元集，因此您可以在行銷報告中使用任何語言。 </p> <p>聯絡您的帳戶管理員或客戶服務，以變更現有報表套裝的多位元組字元支援。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 針對此套裝啟動 Ad Hoc Analysis</span> </td> 
   <td colname="col2"> 可在執行 Ad Hoc Analysis 時檢視此報表套裝。 </td> 
  </tr> 
 </tbody> 
</table>


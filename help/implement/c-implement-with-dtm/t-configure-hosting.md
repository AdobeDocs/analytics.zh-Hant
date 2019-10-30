---
description: 您可使用一或多個可用的託管選項來部署動態標籤管理。
keywords: Analytics 實施;實施方法;Dynamic Tag Management;DTM;託管;託管選項;Akamai;自家託管;自家託管;FTP 傳送;FTP 託管;程式庫下載
seo-description: 您可使用一或多個可用的託管選項來部署動態標籤管理。
seo-title: 設定託管選項
solution: Analytics
title: 設定託管選項
topic: 開發人員和實作
uuid: 04268f2d-e76f-4fe4-8fcc-f0db3a016502
translation-type: ht
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 設定託管選項

您可使用一或多個可用的託管選項來部署 [!UICONTROL Dynamic Tag Management]。

[!UICONTROL 動態標籤管理提供一些管理必要 JavaScript 檔案的選項。]

如需託管的相關詳細資訊，請參閱 [!UICONTROL Dynamic Tag Management] 產品文件中的[內嵌程式碼和託管選項](https://marketing.adobe.com/resources/help/zh_TW/dtm/deployment.html)。

在「內嵌」標籤上，選取託管選項。

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代管選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 實施 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> 實施起來最簡單的代管選項。 </p> <p>遍佈全球的傳送網路。 </p> <p>新增額外第三方基礎架構相依性 (DNS 查閱、Akamai 可用性)。 </p> <p>如需詳細資訊，請參閱動態標籤管理產品文件中的 <a href="https://marketing.adobe.com/resources/help/zh_TW/dtm/akamai.html" format="html" scope="external">Akamai</a>。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">動態標籤管理產生自訂 JavaScript 程式庫。 </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">動態標籤管理將自訂 JavaScript 程式庫匯出至 Akamai。 </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">目標網站直接在頁面層級參考 Akamai 上裝載的動態標籤管理程式庫。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自家代管: FTP 傳送 </td> 
   <td colname="col2"> <p><span class="term">推送</span>方法，是指讓 Dynamic Tag Management 透過 FTP 通訊協定，將自訂 JavaScript 程式庫直接匯出至 Web 內容伺服器。 </p> <p>此解決方案需要有 FTP 伺服器且 Web 內容伺服器上有憑證，以便發佈自訂動態標籤管理程式庫中的變更。 </p> <p>如需詳細資訊，請參閱動態標籤管理產品文件中的 <a href="https://marketing.adobe.com/resources/help/zh_TW/dtm/deployment_ftp.html" format="html" scope="external">FTP</a>。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">動態標籤管理產生自訂 JavaScript 程式庫。 </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">動態標籤管理透過 FTP 將自訂 JavaScript 程式庫匯出至主機伺服器。 </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">目標網站本機參考自訂動態標籤管理程式庫。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自家代管: 程式庫下載 </td> 
   <td colname="col2"> <p><span class="term">提取</span>方法，是指讓應用程式匯出自訂 JavaScript 程式庫 <!-- to Amazon S3-->。然後，裝載於伺服器端的程序便可從從該處存取程式庫。 </p> <p>另外，程式庫也可以供直接從動態標籤管理介面，透過 Web 下載取得。 </p> <p>此解決方案需要手動擷取並發佈動態標籤管理程式庫，或需要建立自動化程序以將程式庫從 Akamai 提取至 Web 內容伺服器。 </p> <p>此方法設定起來最為耗時，但也是最為安全和最具彈性的選項。 </p> <p>若要檢查是否參考了最新版本的程式庫檔案，請使用命令 </p> <p>如需詳細資訊，請參閱動態標籤管理產品文件中的 <a href="https://marketing.adobe.com/resources/help/zh_TW/dtm/deployment_download.html" format="html" scope="external">程式庫下載</a>。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">動態標籤管理產生自訂 JavaScript 程式庫。 </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">動態標籤管理將自訂 JavaScript 程式庫匯出至 Akamai。 </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">手動或用程式將自訂動態標籤管理程式庫移至 Web 內容伺服器。 </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">目標網站本機參考自訂動態標籤管理程式庫。 </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

您可以使用多種託管選項。例如，您可以使用 Akamai 託管階段檔案，而自家託管產品網站。請注意，每種託管類型都有自己的內嵌程式碼，且僅能將一個內嵌程式碼新增至頁面。

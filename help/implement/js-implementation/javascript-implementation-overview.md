---
description: 資料必須傳送至報表套裝以顯示於報表中，才能開始使用 Analytics。
keywords: Analytics實作；javascript；javascript實施；appmeasurement；下載appmeasurement；Identity Service；visitorapi. js；快取；appmeasurement compression
seo-description: 資料必須傳送至報表套裝以顯示於報表中，才能開始使用 Analytics。
seo-title: JavaScript實作概述
solution: Analytics
title: JavaScript實作概述
topic: 開發人員和實施
uuid: bb661d8c-faf9-4454-ac3 c-0c1 a4 c0 a9336
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# JavaScript實作概述

資料必須傳送至報表套裝以顯示於報表中，才能開始使用 Analytics。

The easiest and recommended way to send data to [!DNL Analytics] is by using [Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md). 但是，某些情況下，您可能會想使用舊式的 JavaScript 方法實施 Analytics。

>[!NOTE]
>
>本節說明實施Analytics的舊方法。所有 Analytics 客戶皆能夠存取[動態標籤管理](https://marketing.adobe.com/resources/help/en_US/dtm/)，這是部署 Experience Cloud 標籤的標準方法。

## 實施步驟 {#section_73961BAD5BB4430A95E073DE5C026277}

若想順利實施具有程式碼的頁面來收集資料，您必須能夠存取您的主控伺服器以便將新內容上傳至網站。此外，讓現有網站實施程式碼，也會有幫助。

下列步驟將帶領您進行基本的 Analytics 實施。

<table id="table_1683413EA0E34DBC9291832647B68E96"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> 步驟 </th> 
   <th colname="col1" class="entry"> 任務 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <img  src="assets/step1_icon.png" id="image_21F30BBFC0A249F8B0E1A50EBBEED77D" /> </td> 
   <td colname="col1"> 下載 JavaScript 適用的 AppMeasurement 和訪客 ID 服務。 </td> 
   <td colname="col2"> <p>您可從<a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=code_manager_admin" format="http" scope="external">代碼管理器</a>進行下載。 </p> <p>此下載 zip 包中包含多個檔案。<code>AppMeasurement.js</code> 和 <code>VisitorAPI.js</code> 為實施 Analytics 時的相關檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> 設定Identity Service。 </td> 
   <td colname="col2"> <p>(Formerly <span class="term"> Visitor ID service </span>.) See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html" format="https" scope="external"> Set Up the Identity Service for Analytics </a>. </p> 
    <draft-comment> 
     <p>在 <code>VisitorAPI.js</code> 中，將下列訪客 ID 初始化程式碼加入至檔案開頭處: </p> 
     <code class="syntax javascript">var visitor= Visitor. getInstance(「INSERT-MCORG-ID-HERE」)；visitor. trackingServer=「INSERT-TRACKING-SERVER-HERE」；//與s. trackingServer visitor. trackingServerSecure=「INSERT-SECURE-TRACKING-SERVER-HERE」相同；//sameas s. trackingServerSecure/*== DO NOT ALTER ANYTHING THIS BELOW ThIS== </code>
      <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> 「INSERT-MCORG-ID-HERE」 </code> -(必要)此Adobe Experience Cloud組織ID會在您的公司布建為Adobe Experience Cloud時傳送給您的管理員。 </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code>"INSERT-TRACKING-SERVER-HERE"</code> - (必要) 您的 Analytics 追蹤伺服器。 </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code>"INSERT-SECURE-TRACKING-SERVER-HERE"</code> - (如果啟用 ssl，則為必要) 您的 Analytics 安全追蹤伺服器。 </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> 更新 <code>AppMeasurement.js</code>。 </td> 
   <td colname="col2"> <p>複製 <a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_4351543F2D6049218E18B48769D471E2" format="dita" scope="local">AppMeasurement.js 範例程式碼</a>並貼至 <code>AppMeasurement.js</code> 檔案的開頭處。至少更新下列變數: </p> 
    <ul id="ul_62FA640BD2604E589650A92158272615"> 
     <li id="li_54E56B483B3A416EA27D7B540D60E39F"> <code> s.account="INSERT-RSID-HERE" </code> </li> 
     <li id="li_00A958289BB045379B436F13287E03D5"> <code> s.trackingServer="INSERT-TRACKING-SERVER-HERE" </code> </li> 
     <li id="li_C0779ADF780440ED876236AEB1FB5DCC"> <code> s.visitorNamespace = "INSERT-NAMESPACE-HERE" </code> </li> 
     <li id="li_93072B656C134D8C89195B7F2D7D8F05"> <code> s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE") </code> </li> 
    </ul> <p> See <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly populate the trackingServer and trackingServerSecure variable </a> or contact Client Care if you are unsure about any of these values. 如果變數未正確設定，您的實施將無法正確收集資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_B255E5EAE7BB43FC946D0E9DFCA83003" /> </td> 
   <td colname="col1"> 放置 <code>AppMeasurement.js</code> 和 <code>VisitorAPI.js</code>。 </td> 
   <td colname="col2"> <p>這些核心 JavaScript 檔案必須放置您網站所有頁面都能存取的網站伺服器上。下一個步驟需要用到這些檔案的路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step5_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> 在所有網站頁面上參考 <code>AppMeasurement.js</code> 和 <code>VisitorAPI.js</code>。 </td> 
   <td colname="col2"> <p> 在每一頁的 <code>&lt;head&gt;</code> 或 &lt;body&gt; 標籤中新增下列程式碼行，加入訪客 ID 服務。<code> VisitorAPI.js</code> 必須放在 <code>AppMeasurement.js</code> 之前 : </p> 
    <code class="syntax html">&lt; script language=「JavaScript」type=「text/javascript」src=「Social」&gt;&lt;/script&gt; </code>
  <p> 在每一頁的 <code>&lt;head&gt;</code> 或 <code>&lt;body&gt;</code> 標籤中新增下列程式碼行，加入 JavaScript 適用的 AppMeasurement: </p> 
    <code class="syntax html">&lt; script language=「JavaScript」type=「text/javascript」src=「Social」&gt;&lt;/script&gt; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step6_icon.png" id="image_1C4293CA98F04EE2ADA69EAB95BDE8B1" /> </td> 
   <td colname="col1"> 更新並部署頁面程式碼。 </td> 
   <td colname="col2"> <p>複製<a href="../../implement/js-implementation/appmeasure-mjs-pagecode.md#section_042412C29CC249E298F19B2BC2F43CE7" format="dita" scope="local">頁面程式碼範例</a>並將其貼至您要追蹤之每一頁的開頭 <code>&lt;body&gt;</code> 標籤後面。至少更新下列變數: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step7_icon.png" id="image_A423CBF386AF4E5986E8CBB6E31CD3E5" /> </td> 
   <td colname="col1"> 使用 DigitalPulse 除錯程式驗證是否有傳送資料。 </td> 
   <td colname="col2"> <p>安裝  <a href="../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2" format="dita" scope="local">Adobe Debugger</a> 書籤小程式安裝後，載入您已部署頁面程式碼的頁面並開啟除錯程式。除錯程式會顯示已傳送之收集資料的詳細資料. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 快取 {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript 檔案初始載入後會置於訪客瀏覽器的快取中，通常一個工作階段不會下載超過一次。此檔案即使用於網站上的每個頁面，也不會下載至每個頁面上。大部分網站上的使用者每個工作階段會進行多次頁面檢視，所以將多次使用的 JavaScript 傳輸至此檔案可以減少整體下載資料量。

## 壓縮 JavaScript 適用的 AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

若您對 H 程式碼的頁面寬度 (大小) 有所顧慮 (JavaScript 1.0 適用的 AppMeasurement 會預先壓縮)，Adobe 建議您考慮使用 GZIP 來壓縮此檔案。GZIP 受到所有主要瀏覽器的支援，且在壓縮及解壓縮核心 [!DNL s_code.js] JavaScript 檔案的效能上，都優於 JavaScript 壓縮。

下列連結有助於說明如何使用 GZIP 功能在您的網站上處理 [!DNL s_code.js] JavaScript 程式碼的壓縮: 

[Apache 模組 mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[使用 Tomcat 和 Flex 啟用 gzip 壓縮](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)

---
description: 'null'
title: 實作藍圖
uuid: 988bcca5-67ae-4e3f-97e6-6a42030b1962
translation-type: tm+mt
source-git-commit: 9d0b8e1e9bc2d92fb949ceed7bcfaa31818d02b8

---


# 實施藍圖

## 新使用者 {#section_77433E4FC5ED4C6BAFC1E72EB61C4503}

若您為 Adobe Analytics 的新手，可以使用 [Adobe Analytics 快速入門](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/)指南，快速建立第一個 Analytics 報表套裝 (資料存放庫)。接著，您可以使用 [Experience Platform Launch](https://docs.adobelaunch.com/) / 部署 Analytics 程式碼。

## 實施藍圖 {#section_E3DD8D199B744FFB9E9B386A44220206}

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
   <td colname="col1"> 選擇實作方法. </td> 
   <td colname="col2"> <p>實施 Analytics 常用的方法包括: </p> <p> 
     <ul id="ul_A7475867861540EFBD77AEE8C6DAD418"> 
      <li id="li_035E2619670F4D04A7F708625A9C01EF"> <a href="https://docs.adobelaunch.com/"> Experience Platform Launch </a> (建議使用) <p>本指南會說明使用 Adobe 網站標籤和行動 SDK 管理功能，需要瞭解的所有內容，以及實施方法。 </p> </li> 
      <li id="li_996FA2F5B0E149399CED391AB5235D8A"> <a href="/help/implement/c-implement-with-dtm/dtm-implementation-overview.md"> Dynamic Tag Management </a> <p>本指南包含 Analytics 專屬的資訊，可引導您完成動態標籤管理的實施。 </p> </li> 
      <li id="li_18E6AD6D864246D0BA26DAA1D91DD811"> <a href="/help/implement/js-implementation/javascript-implementation-overview.md"> JavaScript </a> <p>本指南包含資料收集變數的說明，且詳細說明如何在 JavaScript 中實施資料收集程式碼，其中包括<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html">影片</a>。 </p> </li> 
      <li id="li_85EC7A0AC5E04EE6981ED72A88C5D1FD"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/developer.html"> Analytics SDK </a> <p>使用 Analytics SDK 來管理: </p> <p> 
        <ul id="ul_F67F2E1964724800A84445A36DFB8E86"> 
         <li id="li_9C43F051EB5B4EA7A4C14EC1513DB824"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/analytics_main.html"> iOS 上的行動應用程式 </a> </li> 
         <li id="li_4354E44EB8B3494A88578C1621EF5BAC"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/analytics_main.html"> Android 上的行動應用程式 </a> </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step2_icon.png" id="image_02CFDC007BF1486AA312698EBFFA79F7" /> </td> 
   <td colname="col1"> 設定 Identity 服務。 </td> 
   <td colname="col2"> <p>(先前稱為<span class="term">訪客 ID 服務</span>。)請參閱<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-analytics.html">設定 Analytics 適用的 Identity 服務</a>。 </p> 
    <draft-comment> 
     <p>在 <code> VisitorAPI.js </code> 中，將下列訪客 ID 初始化程式碼加入至檔案開頭處: </p> 
     <code class="syntax javascript">
       var&nbsp;visitor&nbsp;=&nbsp;Visitor.getInstance("INSERT-MCORG-ID-HERE"); 
      visitor.trackingServer&nbsp;=&nbsp;"INSERT-TRACKING-SERVER-HERE";&nbsp;//&nbsp;same&nbsp;as&nbsp;s.trackingServer 
      visitor.trackingServerSecure&nbsp;=&nbsp;"INSERT-SECURE-TRACKING-SERVER-HERE";&nbsp;//same&nbsp;as&nbsp;s.trackingServerSecure 
      /* 
      &nbsp;==============&nbsp;DO&nbsp;NOT&nbsp;ALTER&nbsp;ANYTHING&nbsp;BELOW&nbsp;THIS&nbsp;LINE&nbsp;!&nbsp;============
     </code> 
     <ul id="ul_769BA118CC244308A805079C2CBECC12"> 
      <li id="li_D366EBDE24CB433EA523DB228CB2FAF1"> <code> "INSERT-MCORG-ID-HERE" </code> -（必要）當您的公司布建Adobe Experience cloud時，會將此Adobe Experience cloud組織ID傳送給您的管理員。 </li> 
      <li id="li_4F9704A6A6EA4334A3758F99B8D67C9D"> <code> "INSERT-TRACKING-SERVER-HERE" </code> -（必要）您的Analytics追蹤伺服器。 </li> 
      <li id="li_C578420458D649228E54D9809AF62627"> <code> "INSERT-SECURE-TRACKING-SERVER-HERE" </code> -（若已啟用SSL，則為必要項目）您的Analytics安全追蹤伺服器。 </li> 
     </ul> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step3_icon.png" id="image_76B61DEABE3849CCB39135FDD7399EAA" /> </td> 
   <td colname="col1"> 使用選擇的實施方法更新及部署頁面程式碼。 </td> 
   <td colname="col2"> <p>Place the page code just after the opening <code> &lt;body&gt; </code> tag on each page you want to track. 至少更新下列變數: </p> 
    <ul id="ul_29200A6E8DA14386BDA242AD8B270FEB"> 
     <li id="li_FB24D2CB9241401A83BD13EE342A7810"> <code> var s=s_gi("INSERT-RSID-HERE") </code> </li> 
     <li id="li_463A35BA06CC4618B4AF17CD7E83AED5"> <code> s.pageName="INSERT-NAME-HERE" // for example, s.pageName=document.title </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img  src="assets/step4_icon.png" id="image_844E896941E2489A943BE10AD710ED36" /> </td> 
   <td colname="col1"> 使用 Adobe Experience Cloud Debugger 驗證是否已傳送資料。 </td> 
   <td colname="col2"> <p>安裝 <a href="/help/implement/impl-testing/debugger.md"> Experience Cloud Debugger</a>。安裝後，載入您已部署頁面程式碼的頁面並開啟除錯程式。除錯程式會顯示已傳送之收集資料的詳細資料. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 更多資訊 {#section_64B6A948DF4A4B5E9E1D22549F8C508B}

如需 [!UICONTROL Experience Platform Launch]、[!UICONTROL Dynamic Tag Management] 及 JavaScript 方法之間的差異的相關資訊，請參閱[選擇實施方法](/help/implement/c-implementation-methods/choose-implementation-method.md)。

如需快速入門程序的概述，及快速設定第一個 Analytics 報表套裝的說明，請參閱 Analytics 快速入門指南中的 [Analytics 實施快速入門](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html)。

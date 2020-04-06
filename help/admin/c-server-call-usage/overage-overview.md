---
description: 'null'
title: 伺服器呼叫使用量概觀
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 伺服器呼叫使用量概觀

## 為何要對伺服器呼叫使用量進行監控和傳送警報？{#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics Server呼叫使用可解決您對瀏覽器和行動伺服器呼叫使用資料透明度的要求。 其可讓您存取：

* 「伺服器呼叫使用」控制面板會追蹤您的伺服器呼叫使用資料，並將其與合約限制進行比較。(**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics > Components >Alerts]**)

伺服器呼叫使用量的主要幾項好處如下：

* **洞悉** 您的伺服器呼叫消費和承諾資料，包括與您合約伺服器呼叫使用限制相比的行動使用。
* **提醒** ，通知您超額使用的風險或發生情況，並準備／處理可能發生超額使用的情況。

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. 此外，該資料未包含行動耗用量。此功能也會取代>下 **[!UICONTROL Billing Information]** 的目前 **[!UICONTROL Analytics]** 報表 **[!UICONTROL Reports]** 。

## 必備條件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **權限：**&#x200B;若要存取「伺服器呼叫使用量」控制面板和「警報產生器/管理器」，您必須是 Adobe Analytics 管理員。
* **權限：** 管理員可授予非管理員的存取權：權限稱為 **[!UICONTROL Server Call Usage]**。 請參閱[伺服器呼叫使用量權限](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369)。

## 重要術語 {#section_CBA348A039F34563B097CD8890AB358D}

以下是伺服器呼叫使用量之基本術語的簡短入門：

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 詞語 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫 </p> </td> 
   <td colname="col2"> <p>伺服器呼叫（也稱為「點擊」或「影像要求」）是將資料傳送至Adobe伺服器進行處理的例項。 最常見的伺服器呼叫類型是頁面檢視。 訪客在您的網站上檢視頁面，因此系統向 Adobe 產生伺服器呼叫，要求 Adobe 收集與處理資料，這次檢視就會在報表量度中計為一次頁面檢視。 </p> <p>還有其他類型的伺服器呼叫，包括退出連結和檔案下載，資料會傳送至Adobe進行處理，但不會記錄為新的頁面檢視。 即使是「已排除」的頁面檢視（例如您所設定的IP位址範圍從報表中排除），也是伺服器呼叫，因為Adobe會接收並處理這些檢視，但絕不會顯示在報表中。 </p> <p><b>主要伺服器呼叫</b>：從網站訪客瀏覽器或「資料插入 API」直接收到的請求。包含主要點擊（頁面檢視）、主要自訂事件、主要下載事件和主要退出事件。 </p> <p><b>次要伺服器呼叫</b>：多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。如果次要伺服器呼叫已依VISTA規則移動（未複製）至其他報表套裝，累積的次要伺服器呼叫會從主要伺服器呼叫中扣除。 </p> <p><b>行動主要伺服器呼叫 </b> </p> <p>直接從其中一個行動 SDK 收到的請求。包含 trackAction、trackState、trackApp Crashes、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease。</p> <p><b>行動次要伺服器呼叫</b> </p> <p>多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。如果次要伺服器呼叫已依VISTA規則移動（未複製）至其他報表套裝，累積的次要伺服器呼叫會從主要伺服器呼叫中扣除。 </p> <p>注意：如果貴公司在合約上僅有權使用行動伺服器呼叫 (主要或次要)，則您的 Web 和行動專屬使用量將會以您的行動專屬承諾使用量為計算基準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳單公司（帳單ID） </p> </td> 
   <td colname="col2"> <p>為伺服器呼叫計費的合法實體。 例如 adobe.com。每個帳單公司都有一個帳單ID，用來唯一識別帳單客戶。 帳單ID可能會系結至多個Experience Cloud組織；組織與帳單ID之間並不總是1:1的關係。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登入公司 </p> </td> 
   <td colname="col2"> <p>一間帳單公司可以擁有<a href="https://helpx.adobe.com/tw/analytics/kb/multiple-login-companies.html">多家登入公司</a>。登入公司是貴組織使用之報表套裝的集合。 有些組織有多個登入公司，可套用至組織的不同部分。 這對於處理不同業務單位的大型組織特別有用，因為許多報表套裝不適用於公司內的其他人。 </p> <p>通常，這些公司是一家公司的地區子公司。 此範例顯示登入公司及其相關的報表套裝： </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide：RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us：RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in：RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de：RS4 </li> 
    </ul> <p>注意：具有相關<u>權限</u>之所有使用者皆可看到帳單公司內<a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">所有</a>報表套裝的伺服器呼叫使用量資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud組織 </p> </td> 
   <td colname="col2"> <p> 組織是可讓管理員設定群組和使用者，以及控制 Experience Cloud 單一登入的實體。組織的作用就像跨及所有 Experience Cloud 產品和解決方案的登入公司。 </p> <p>通常，組織就是您的公司名稱。 但是，公司可以有許多組織。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫承諾 </p> </td> 
   <td colname="col2"> <p>當貴公司與Adobe簽訂合約時，Adobe銷售團隊會與您、客戶、類型（主要、次要、行動主要、行動次要）以及您在合約期間預計會發生的伺服器呼叫數目。 這是您對伺服器呼叫的總承諾。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期 </p> </td> 
   <td colname="col2"> <p>為了監控伺服器呼叫的使用情況，這項伺服器呼叫總承諾會細分為較短的使用期（例如3個月），以利年與年的比較。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合約期間 </p> </td> 
   <td colname="col2"> <p>合約期限可以跨多年。 假設您的公司已簽約600萬次伺服器呼叫，期限為3年。 如要監控伺服器呼叫使用量，您可將這個 3 年期間劃分為較小的使用期間，以便進行逐年比較。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 伺服器呼叫使用量權限 {#section_FCC58EB635954A32990D4E67B52B4369}

「伺服器呼叫使用」權限會自動授予Analytics管理員。 它可讓使用者檢視控制面板並建立伺服器呼叫警報。 管理員可以選擇將此權限授與非管理員。

>[!NOTE] 貴公司可選擇哪些登入公司能存取「伺服器呼叫使用量」。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 權限名稱 </th> 
   <th colname="col3" class="entry"> 如果您登入Adobe Analytics，請授予權限（舊版登入） </th> 
   <th colname="col4" class="entry"> 如果您已登入Adobe Experience Cloud，請授予權限 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫使用量 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">透過sc.omniture.com登入Analytics。 </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">導覽至<span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">使用者管理</span> &gt; <span class="uicontrol">群組</span> &gt; <span class="uicontrol">編輯所有報表存取</span> &gt; <span class="uicontrol">分析工具</span> &gt; <span class="uicontrol">自訂</span> &gt; <span class="uicontrol">伺服器呼叫使用量」</span></span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">登入 login.experiencecloud.adobe.com。</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">按一下<span class="uicontrol">「Analytics」</span>。 </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">導覽至<span class="ignoretag"><span class="uicontrol">「產品</span> &gt; <span class="uicontrol">產品設定檔</span> &gt; <span class="uicontrol">權限</span> &gt; <span class="uicontrol">分析工具</span> &gt; <span class="uicontrol">伺服器呼叫使用量」</span></span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>


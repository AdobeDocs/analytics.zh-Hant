---
description: 'null'
seo-description: 'null'
seo-title: 伺服器呼叫使用量概述
title: 伺服器呼叫使用量概述
uuid: 6e014364-efc1-4769-a0 b5-cf105 c0 ed9 b1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 伺服器呼叫使用量概述

## 為何要對伺服器呼叫使用量進行監控和傳送警報? {#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics 伺服器呼叫使用量可滿足您對瀏覽器和行動伺服器呼叫使用量資料透明化的請求。其可讓您存取:

* 「伺服器呼叫使用量」控制面板，用於追蹤伺服器呼叫耗用量資料，並將其與合約限制進行比較。(**[!UICONTROL 「分析 &gt; 管理員 &gt; 伺服器呼叫使用量」]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics &gt; Components &gt;Alerts]**)

伺服器呼叫使用量的主要幾項好處如下:

* 伺服器呼叫耗用量和承諾使用量資料的&#x200B;**可見性**，包括相對於合約伺服器呼叫使用量限制的行動耗用量。
* **警報**&#x200B;功能可通知您風險狀況或使用過量情形，並對於發生使用過量的可能性加以因應/採取行動。

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. 此外，該資料未包含行動耗用量。This feature will also replace the current **[!UICONTROL Billing Information]** report under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** .

## 必備條件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **權限**: 若要存取「伺服器呼叫使用量」控制面板和「警報產生器/管理器」，您必須是 Adobe Analytics 管理員。
* **權限**：管理員可以授與非管理員的存取權：權限稱為 **[!UICONTROL 「伺服器呼叫使用情形]**」。請參閱[伺服器呼叫使用量權限](../../admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## 重要術語 {#section_CBA348A039F34563B097CD8890AB358D}

以下是伺服器呼叫使用量之基本術語的簡短入門:

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 術語 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫 </p> </td> 
   <td colname="col2"> <p>伺服器呼叫又稱為「點擊」或「影像要求」，是有關資料傳送到 Adobe 伺服器進行處理的一項實例。伺服器呼叫最常見的類型是頁面檢視。當訪客在您的網站上檢視頁面並呼叫伺服器呼叫時，會發生頁面檢視，並將資訊收集、處理和包含在您的報表量度中。 </p> <p>另外還有其他類型的伺服器呼叫，包括退出連結與檔案下載；在此處資料會傳送至 Adobe 進行處理，但這些呼叫不會記錄為新的頁面檢視。即使是「已排除的」頁面檢視 (例如，被您所設定的 IP 位址範圍排除在報告外) 也是伺服器呼叫，因為這些檢視都會由 Adobe 接收並處理，但一律不會在您的報告中顯示。 </p> <p><b>主要伺服器呼叫</b>: 從網站訪客瀏覽器或「資料插入 API」直接收到的請求。包含主要點擊 (頁面檢視)、主要自訂事件、主要下載事件，以及主要退出事件。 </p> <p><b>次要伺服器呼叫</b>: 多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。如果次要伺服器呼叫次數已按照 VISTA 規則移動 (非複製) 至其他報表套裝，累積的次要伺服器呼叫次數將從主要伺服器呼叫次數中扣除。 </p> <p><b>行動主要伺服器呼叫</b> </p> <p>直接從其中一個Mobile SDK收到請求。包括trackAction、trackState、trackApp Crues、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrement。</p> <p><b>行動次要伺服器呼叫</b> </p> <p>多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。如果次要伺服器呼叫次數已按照 VISTA 規則移動 (非複製) 至其他報表套裝，累積的次要伺服器呼叫次數將從主要伺服器呼叫次數中扣除。 </p> <p>注意: 如果貴公司在合約上僅有權使用行動伺服器呼叫 (主要或次要)，則您的 Web 和行動專屬使用量將會以您的行動專屬承諾使用量為計算基準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳單公司 (計費 ID) </p> </td> 
   <td colname="col2"> <p>為伺服器支付收取費用的合法實體。例如 adobe.com。 每個「帳單公司」都有一個「計費 ID」，用於專門識別計費客戶。計費 ID 可以綁定多個 Experience Cloud 組織；組織與計費 ID 之間並非總是 1:1 的關係。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登入公司 </p> </td> 
   <td colname="col2"> <p>一間帳單公司可以擁有<a href="https://helpx.adobe.com/analytics/kb/multiple-login-companies.html" format="html" scope="external">多家登入公司</a>。登入公司是您的組織使用的報表套裝集合。某些組織擁有多個登入公司，適用於組織內的不同部門。在需要處理不同業務單位的大型組織中，有許多報表套裝不適用於公司內其他人時，這特別有用。 </p> <p>通常會是公司的地區子公司。此範例顯示登入公司及其相關的報表套裝: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide: RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>注意: 具有相關<u>權限</u>之所有使用者皆可看到帳單公司內<a href="../../admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369" format="dita" scope="local">所有</a>報表套裝的伺服器呼叫使用量資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud 組織 </p> </td> 
   <td colname="col2"> <p>組織是可讓管理員設定群組及使用者，以及控制 Experience Cloud 中單一登入的實體。組織的運作方式就像登入公司，涵蓋所有Experience Cloud產品和解決方案。 </p> <p>最常見的組織就是您的公司名稱。不過，公司可以有許多組織。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫承諾使用量 </p> </td> 
   <td colname="col2"> <p>當貴公司與 Adobe 簽訂合約時，Adobe 銷售團隊會向您、客戶、類型 (主要、次要、行動主要、行動次要)，以及您希望在合約期間內發生的大致伺服器呼叫次數進行識別。這是您的伺服器呼叫承諾使用量總計。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期間 </p> </td> 
   <td colname="col2"> <p>基於伺服器呼叫使用量監控目的，該伺服器呼叫承諾使用量總計劃分為較小的使用期間 (例如 3 個月)，有助於進行逐年比較。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合約期間 </p> </td> 
   <td colname="col2"> <p>合約期間可以持續多年。假設您的公司有 600 萬次呼叫的伺服器呼叫承諾使用量，合約時間為期 3 年。針對伺服器呼叫使用監控的目的，此三年期間可細分為較小的使用期間，以促進年度比較。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 伺服器呼叫使用量權限 {#section_FCC58EB635954A32990D4E67B52B4369}

伺服器呼叫使用量權限會自動授予 Analytics 管理員。該權限可讓使用者檢視控制面板，並建立伺服器呼叫警報。管理員可以選擇將這些權限授予非管理員使用者。

>[!NOTE]
>
>您的公司可以選擇哪些登入公司可以存取伺服器呼叫使用權。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 權限名稱 </th> 
   <th colname="col3" class="entry"> 在登入 Adobe Analytics (舊登入) 的情況下授予權限 </th> 
   <th colname="col4" class="entry"> 在登入 Adobe Experience Cloud 的情況下授予權限 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫使用量 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">透過 sc.omniture.com 登入 Analytics。 </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">導覽至<span class="ignoretag"><span class="uicontrol">「管理員</span> &gt; <span class="uicontrol">使用者管理</span> &gt; <span class="uicontrol">群組</span> &gt; <span class="uicontrol">編輯所有報表存取</span> &gt; <span class="uicontrol">分析工具</span> &gt; <span class="uicontrol">自訂</span> &gt; <span class="uicontrol">伺服器呼叫使用量」</span></span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">登入login. experiencecloud. adobe. com。</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">按一下<span class="uicontrol">「Analytics」</span>。 </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">導覽至<span class="ignoretag"><span class="uicontrol">「產品</span> &gt; <span class="uicontrol">產品設定檔</span> &gt; <span class="uicontrol">權限</span> &gt; <span class="uicontrol">分析工具</span> &gt; <span class="uicontrol">伺服器呼叫使用量」</span></span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>


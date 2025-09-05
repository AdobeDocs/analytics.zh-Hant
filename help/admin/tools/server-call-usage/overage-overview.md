---
description: Adobe Analytics 伺服器呼叫使用量功能概觀。
title: 伺服器呼叫使用量概觀
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 80%

---

# 伺服器呼叫使用量

Adobe Analytics伺服器呼叫使用量可處理您對瀏覽器和行動伺服器呼叫使用量資料的透明度要求。 其可讓您存取：

* 伺服器呼叫使用量儀表板，可追蹤您的伺服器呼叫使用量資料，並將其與合約限制進行比較。 (在Adobe Analytics中，選取> [!UICONTROL **管理員**] > [!UICONTROL **伺服器呼叫使用量**])
* 警報產生器中的伺服器呼叫使用量警報型別可讓您設定警報，避免使用過量(在Adobe Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **警報**])

伺服器呼叫使用量的主要優點包括：

* 伺服器呼叫耗用量和承諾使用量資料的&#x200B;**可見性**，包括相對於合約伺服器呼叫使用量限制的行動耗用量。
* **警報**&#x200B;功能可通知您風險狀況或使用過量情形，並對於發生使用過量的可能性加以因應/採取行動。

## 先決條件 {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **許可權：**&#x200B;若要存取伺服器呼叫使用量控制面板和警報產生器或警報管理員，您必須是Adobe Analytics管理員。
* **許可權：**&#x200B;系統管理員可以授與非管理員的存取權：該許可權稱為&#x200B;**[!UICONTROL 伺服器呼叫使用量]**。 請參閱[伺服器呼叫使用量許可權](#server-call-usage-permission)。

## 重要術語 {#terminology}

下列辭彙對於瞭解伺服器呼叫使用量相當重要：

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
   <td colname="col2"> <p>伺服器呼叫又稱為「點擊」或「影像要求」，是有關資料傳送到 Adobe 伺服器進行處理的一項實例。伺服器呼叫最常見的類型是頁面檢視。訪客在您的網站上檢視頁面，因此系統向 Adobe 產生伺服器呼叫，要求 Adobe 收集與處理資料，這次檢視就會在報表量度中計為一次頁面檢視。 </p> <p>另外還有其他類型的伺服器呼叫，包括退出連結與檔案下載；在此處資料會傳送至 Adobe 進行處理，但這些呼叫不會記錄為新的頁面檢視。即使是「已排除的」頁面檢視 (例如，被您所設定的 IP 位址範圍排除在報告外) 也是伺服器呼叫，因為這些檢視都會由 Adobe 接收並處理，但一律不會在您的報告中顯示。 </p> <p><b>主要伺服器呼叫</b>：從網站訪客瀏覽器或「資料插入 API」直接收到的請求。包含主要點擊 (頁面檢視)、主要自訂事件、主要下載事件，以及主要退出事件。 </p> <p><b>次要伺服器呼叫</b>：多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。如果次要伺服器呼叫次數已按照 VISTA 規則移動 (非複製) 至其他報告套裝，累積的次要伺服器呼叫次數將從主要伺服器呼叫次數中扣除。 </p> <p><b>行動主要伺服器呼叫</b> </p> <p>直接從其中一個行動 SDK 收到的請求。包含 trackAction、trackState、trackApp Crashes、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease。</p> <p><b>行動次要伺服器呼叫</b> </p> <p>多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。如果次要伺服器呼叫次數已按照 VISTA 規則移動 (非複製) 至其他報告套裝，累積的次要伺服器呼叫次數將從主要伺服器呼叫次數中扣除。 </p> <p>注意：如果貴公司在合約上僅有權使用行動伺服器呼叫 (主要或次要)，則您的 Web 和行動專屬使用量將會以您的行動專屬承諾使用量為計算基準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳單公司（帳單ID） </p> </td> 
   <td colname="col2"> <p>為伺服器支付收取費用的合法實體。例如 adobe.com。每個「帳單公司」都有一個「計費 ID」，用於專門識別計費客戶。計費 ID 可以綁定多個 Experience Cloud 組織；組織與計費 ID 之間並非總是 1:1 的關係。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登入公司 </p> </td> 
   <td colname="col2"> <p>一間帳單公司可以擁有<a href="https://helpx.adobe.com/tw/analytics/kb/multiple-login-companies.html">多家登入公司</a>。登入公司是您的組織使用的報告套裝集合。某些組織擁有多個登入公司，適用於組織內的不同部門。在需要處理不同業務單位的大型組織中，有許多報告套裝不適用於公司內其他人時，這特別有用。 </p> <p>通常會是公司的地區子公司。此範例顯示登入公司及其相關的報告套裝： </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide：RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us：RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in：RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de：RS4 </li> 
    </ul> <p>注意：具有相關<u>權限</u>之所有使用者皆可看到帳單公司內<a href="/help/admin/tools/server-call-usage/overage-overview.md">所有</a>報告套裝的伺服器呼叫使用量資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud 組織 </p> </td> 
   <td colname="col2"> <p> 組織是可讓管理員設定群組和使用者，以及控制 Experience Cloud 單一登入的實體。組織的作用就像跨及所有 Experience Cloud 產品和解決方案的登入公司。 </p> <p>通常組織就是您的公司名稱，但是一間公司可以有多個組織。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫承諾 </p> </td> 
   <td colname="col2"> <p>當貴公司與 Adobe 簽訂合約時，Adobe 銷售團隊會向您、客戶、類型 (主要、次要、行動主要、行動次要)，以及您希望在合約期間內發生的大致伺服器呼叫次數進行識別。這是您的伺服器呼叫承諾使用量總計。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期間 </p> </td> 
   <td colname="col2"> <p>基於伺服器呼叫使用量監控目的，該伺服器呼叫承諾使用量總計劃分為較小的使用期間 (例如 3 個月)，有助於進行逐年比較。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合約期間 </p> </td> 
   <td colname="col2"> <p>合約期間可以持續多年。假設您的公司有 600 萬次呼叫的伺服器呼叫承諾使用量，合約時間為期 3 年。如要監控伺服器呼叫使用量，您可將這個 3 年期間劃分為較小的使用期間，以便進行逐年比較。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 伺服器呼叫使用量許可權 {#permission}

「伺服器呼叫使用量」許可權會自動授與Analytics管理員。 該權限可讓使用者檢視控制面板，並建立伺服器呼叫警報。管理員可以選擇將這些權限授予非管理員使用者。

>[!NOTE]
>
>貴公司可選擇哪些登入公司能存取「伺服器呼叫使用量」。

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
     <li id="li_066D90AB071941C3869EDAFCE981707A">瀏覽至<span class="ignoretag"> <span class="uicontrol">管理員</span> &gt; <span class="uicontrol">所有管理員</span> &gt; <span class="uicontrol">使用者管理</span> &gt; <span class="uicontrol">群組</span> &gt; <span class="uicontrol">編輯所有報表存取權</span> &gt; <span class="uicontrol">分析工具</span> &gt; <span class="uicontrol">自訂</span> &gt; <span class="uicontrol">伺服器呼叫使用量</span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">登入 login.experiencecloud.adobe.com。</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">按一下<span class="uicontrol">「Analytics」</span>。 </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">導覽至<span class="ignoretag"> <span class="uicontrol">產品</span> &gt; <span class="uicontrol">產品設定檔</span> &gt; <span class="uicontrol">許可權</span> &gt; <span class="uicontrol">分析工具</span> &gt; <span class="uicontrol">伺服器呼叫使用量</span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

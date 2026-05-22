---
description: Adobe Analytics 伺服器呼叫使用量功能概觀。
title: 伺服器呼叫使用量概觀
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
role: Admin
TQID: https://experienceleague.adobe.com/-IIz9r-K-flZq85Dz3lhYuo9-Ko0zt0KoJJ7DtI5Mz4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 1013
ht-degree: 38%

---

# 伺服器呼叫使用量

Adobe Analytics伺服器呼叫使用量可處理您對瀏覽器和行動伺服器呼叫使用量資料的透明度要求。 其可讓您存取：

* 伺服器呼叫使用量儀表板，可追蹤您的伺服器呼叫使用量資料，並將其與合約限制進行比較。 （在Adobe Analytics中，選取> [!UICONTROL **管理員**] > [!UICONTROL **伺服器呼叫使用量**]）
* 警報產生器中的伺服器呼叫使用量警報型別可讓您設定警報，避免使用過量（在Adobe Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **警報**]）

伺服器呼叫使用量的主要優點包括：

* **可檢視您的伺服器呼叫使用量和承諾使用量資料**，包括相對於合約伺服器呼叫使用量限制的行動使用量。
* **警示**，通知您發生超額的風險或發生超額的情況，並準備/採取行動，以防發生超額的情況。

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
   <td colname="col2"> <p>伺服器呼叫又稱為「點擊」或「影像要求」，是有關資料傳送到 Adobe 伺服器進行處理的一項實例。 最常見的伺服器呼叫型別是頁面檢視。 訪客在您的網站上檢視頁面，因此系統向 Adobe 產生伺服器呼叫，要求 Adobe 收集與處理資料，這次檢視就會在報表量度中計為一次頁面檢視。 </p> <p>還有其他型別的伺服器呼叫，包括退出連結和檔案下載，資料會傳送至Adobe進行處理，但不會記錄為新頁面檢視。 甚至「已排除」的頁面檢視（例如，根據您設定的IP位址範圍從報表中排除）也是伺服器呼叫，因為它們會由Adobe接收及處理，但永遠不會顯示在報表中。 </p> <p><b>主要伺服器呼叫</b>：從網站訪客瀏覽器或「資料插入 API」直接收到的請求。 包括主要點選（頁面檢視）、主要自訂事件、主要下載事件和主要退出事件。 </p> <p><b>次要伺服器呼叫</b>：多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。 如果次要伺服器呼叫次數已按照 VISTA 規則移動 (非複製) 至其他報告套裝，累積的次要伺服器呼叫次數將從主要伺服器呼叫次數中扣除。 </p> <p><b>行動主要伺服器呼叫</b> </p> <p>直接從其中一個行動 SDK 收到的請求。 包含 trackAction、trackState、trackApp Crashes、trackActionFromBackground、trackLocation、trackBeacon、trackPushMessageClickThrough、trackTimedActionBacklog、trackLifetimeValueIncrease。</p> <p><b>行動次要伺服器呼叫</b> </p> <p>多套裝標記所建立或按照 VISTA 規則複製/移動之主要伺服器呼叫次數的重複份數。 如果次要伺服器呼叫次數已按照 VISTA 規則移動 (非複製) 至其他報告套裝，累積的次要伺服器呼叫次數將從主要伺服器呼叫次數中扣除。 </p> <p>注意：如果貴公司在合約上僅有權使用行動伺服器呼叫 (主要或次要)，則您的 Web 和行動專屬使用量將會以您的行動專屬承諾使用量為計算基準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帳單公司（帳單ID） </p> </td> 
   <td colname="col2"> <p>為伺服器呼叫計費的法人。 例如 adobe.com。 每個帳單公司都有一個用於唯一識別帳單客戶的帳單ID。 帳單ID可以繫結至多個CX Enterprise組織；組織與帳單ID之間並不一定存在1:1關係。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登入公司 </p> </td> 
   <td colname="col2"> <p>一間帳單公司可以擁有<a href="https://helpx.adobe.com/tw/analytics/kb/multiple-login-companies.html">多家登入公司</a>。 登入公司是您的組織使用的報告套裝集合。 某些組織擁有多個登入公司，適用於組織的不同部分。 在需要處理不同業務單位的大型組織中，有許多報告套裝不適用於公司內其他人時，這特別有用。 </p> <p>這些通常是公司的地區子公司。 此範例顯示登入公司及其相關的報告套裝： </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide：RS1、RS2、RS3、RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us：RS1、RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in：RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de：RS4 </li> 
    </ul> <p>注意：具有相關<u>權限</u>之所有使用者皆可看到帳單公司內<a href="/help/admin/tools/server-call-usage/overage-overview.md">所有</a>報告套裝的伺服器呼叫使用量資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CX Enterprise組織 </p> </td> 
   <td colname="col2"> <p>組織是可讓管理員設定群組和使用者，以及控制CX Enterprise單一登入的實體。 組織的作用就像一個登入公司，涵蓋所有CX Enterprise產品和解決方案。 </p> <p>通常組織就是您的公司名稱， 但是一間公司可以有多個組織。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫承諾 </p> </td> 
   <td colname="col2"> <p>當貴公司與Adobe簽訂合約時，Adobe銷售團隊會向您、客戶識別型別（主要、次要、行動主要、行動次要），以及您預期在合約期間內會發生的大約伺服器呼叫次數。 這是您的伺服器呼叫承諾使用總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用期間 </p> </td> 
   <td colname="col2"> <p>為了監控伺服器呼叫使用量，這項伺服器呼叫承諾使用量總計會細分為較小的使用期間（例如3個月），以便進行逐年比較。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合約期間 </p> </td> 
   <td colname="col2"> <p>合約期間可以跨越多年。 假設您的公司在3年的合約時間內有600萬次伺服器呼叫承諾。 如要監控伺服器呼叫使用量，您可將這個 3 年期間劃分為較小的使用期間，以便進行逐年比較。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 伺服器呼叫使用量許可權 {#permission}

「伺服器呼叫使用量」許可權會自動授與Analytics管理員。 它可讓使用者檢視控制面板，並建立伺服器呼叫警報。 管理員可以選擇將此許可權授予非管理員。

>[!NOTE]
>
>貴公司可選擇哪些登入公司能存取「伺服器呼叫使用量」。

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 權限名稱 </th> 
   <th colname="col3" class="entry"> 如果您已登入Adobe Analytics （舊版登入），請授予許可權 </th> 
   <th colname="col4" class="entry"> 如果您已登入Adobe CX Enterprise，請授與許可權 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>伺服器呼叫使用量 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">透過sc.omniture.com登入Analytics。 </li> 
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

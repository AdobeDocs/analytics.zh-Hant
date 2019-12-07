---
description: 虛擬報表套裝新使用者適用的提示和最佳實務。
keywords: Virtual Report Suite
title: VRS 常見問題集
topic: Reports and analytics
uuid: 91225743-765a-4145-9ce5-4268e80ea7e8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# VRS 常見問題集

虛擬報表套裝新使用者適用的提示和最佳實務。

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>我應該將多個報表套裝的實施合併成單一的「全域」報表套裝，然後使用虛擬報表套裝來公開不同的資料區段給使用者嗎?</b> </td> 
   <td colname="col2"> <p>看情形。以下是一些您應<b>考慮繼續使用個別報表套裝</b>的情形: </p> 
    <ul id="ul_493454A655DE48E0AF94130014203268"> 
     <li id="li_B37C2651D2804FD1B965286C85A765D5">如果您的變數/維度具有大量獨特值，將它們合併成單一報表套裝，可能會使您在此全域套裝中超過每月的獨特值限制，繼而造成截斷 (在報表中顯示為「低流量」行項目)。 </li> 
     <li id="li_87ABC62EC73D4355A9F768AD1949D3C6">如果您需要個別資料區段的即時或「目前的資料」報告 (例如品牌、業務部門等)。 </li> 
     <li id="li_7252787B2D4C4756836DAEA0EEC0BF8B">如果您的各種報表套裝具有獨特的追蹤需求 (亦即，各報表套裝使用 Adobe Analytics 變數和事件的方式極為不同)，請注意合併成全域報表套裝並不會授與您額外的變數和事件用於追蹤。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>虛擬報表套裝上的哪些設定是繼承自父報表套裝?</b> </td> 
   <td colname="col2"> <p>虛擬報表套裝 (VRS) 繼承父報表套裝的大部分服務層級，例如 eVar 設定、處理規則、分類等。 </p> <p>但<b>不</b>繼承下列設定: </p> 
    <ul id="ul_43B0637F095C480B82126C96BFF627FA"> 
     <li id="li_F3DF9D6B0B1A4A46B9D8B1CF2DA09BE3">報表套裝 ID </li> 
     <li id="li_A735D7BA4DA14DCB8F40D7898A324F1F">報表套裝名稱 </li> 
     <li id="li_BF66DD426EE7464CBF7F2EB56B0C3075">權限群組 (虛擬報表套裝可以指派給自己的權限群組) </li> 
    </ul> <p>注意: 這不包括大部分使用者建立的實體，例如書籤、控制面板、排程報表等，這些項目不會從父項繼承，也不能專門針對 VRS 建立和使用 (將於下一個問題更詳細說明)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>在 Analytics UI 中使用虛擬報表套裝，和使用基本報表套裝有何不同?</b> </td> 
   <td colname="col2"> <p>虛擬報表套裝一旦建立後，就會在整個 UI 中被視為基本報表套裝，通常也支援對其使用大部分的擴充功能。例如: </p> 
    <ul id="ul_D20435FD9B3546DFB611FD09035BACBB"> 
     <li id="li_4A331EB50B7F43E697F67B4A657B4450">虛擬報表套裝會像其他基本報表套裝一樣顯示在報表套裝選取器中，也可供個別選取。 </li> 
     <li id="li_6E8C1E45C68943A1BA7C260FA62C40E0">DL 報表、書籤、控制面板、目標、警報、區段、計算量度等都可對虛擬報表套裝建立，且獨立於父項操作。 </li> 
     <li id="li_5701D7F60BF8452CBEC8DFA2072CE8C2">虛擬報表套裝可以像其他報表套裝一樣，個別新增至權限群組。 </li> 
     <li id="li_764475FD352C434D92E876E30699F280">在 VRS 範圍內執行報表時仍可套用區段，這些區段在擷取報表資料時會自動與虛擬報表套裝的區段一起堆疊。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>管理控制台和管理員 API 如何對待虛擬報表套裝? 我可以像基本報表套裝那樣對其儲存功能嗎? </b> </td> 
   <td colname="col2"> <p>不行，虛擬報表套裝<b>不支援大部分的管理員功能</b>。如上所述，VRS 繼承父項的大部分的服務層級和功能 (例如 eVar 設定、處理規則、分類等)，所以若想在 VRS 上對這些繼承設定進行變更，您必須改變父報表套裝。 </p> <p>因此，虛擬報表套裝<b>只會顯示</b>在 UI 的這些位置: </p> 
    <ul id="ul_64CF126ACF39453A95BD9FC9D2CFA59B"> 
     <li id="li_08EBF87ADF13400C9DD3FFC2695F5CF9">虛擬報表套裝管理器，您可在此處建立和編輯 VRS。 <p>( <span class="ignoretag"> <span class="uicontrol"> 分析</span> &gt; <span class="uicontrol">元件</span> &gt; <span class="uicontrol">虛擬報表套裝 </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> 使用者管理介面，您可在此處編輯自訂權限群組。如此可讓您新增 VRS 帳戶至權限群組，也可將 VRS 帳戶用來建立只具備虛擬報表套裝存取權的群組 (如果管理員希望拒絕對父項的存取，並只允許使用者存取特定區段)。 <p>( <span class="ignoretag"> <span class="uicontrol"> 管理員</span> &gt; <span class="uicontrol">使用者管理 </span> </span>) </p> </li> 
    </ul> <p>注意: 當您使用網站服務 API 並嘗試對 VRS 儲存功能設定時，會發生例外狀況。您只能對基本報表套裝設定功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>SiteCatalyst 14 UI 支援虛擬報表套裝嗎?</b> </td> 
   <td colname="col2"> <p>否，我們未在 SiteCatalyst 14 中開放虛擬報表套裝。虛擬報表套裝不會在報表套裝選取器中顯示為選擇項目，也無法加以選取。不過，在編輯群組時，我們會在 SiteCatalyst 14 管理控制台中開放虛擬報表套裝。在這種特殊情況下，應將虛擬報表套裝適當表示，以免從可能具一/多個虛擬報表套裝存取權的現有群組中被意外移除。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>我已勾選「啟動後開始新的造訪」。為什麼我看到的造訪次數還是遠高於啟動次數?</b> </td> 
   <td colname="col2"> <p> 勾選<span class="uicontrol">「啟動後開始新的造訪」</span>選項後，逾時仍然適用。因此，如果使用者使用某應用程式 10 分鐘，且在執行各動作間休息 1 分鐘，新的造訪就會在啟動後開始，而當造訪逾時發生時，會建立額外 9 個造訪次數。若要在使用<span class="uicontrol">「啟動後開始新的造訪」</span>選項後，使啟動次數和造訪次數盡可能接近，則使用的逾時時間應較 SDK 中設定之作業逾時時間來得長。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>我已設定「啟動後開始新的造訪」且設定的逾時時間較 SDK 的長。為什麼我的啟動次數仍遠低於造訪次數?</b> </td> 
   <td colname="col2"> <p> 如果逾時時間比 SDK 中設定的值來得長，則您的應用程式很可能會在背景時就傳入點擊，而這些點擊會登錄為新的造訪。請透過父報表套裝中的點擊類型維度查看，檢視是否有任何背景點擊。 </p> <p> <p>注意: 背景和前景點擊僅可在 SDK 4.13.6 版及更高版本中區別。如果您使用較低版本，則所有點擊都會顯示為前景。如果您使用正確的 SDK 版本，應啟用<span class="uicontrol">「避免背景點選計數為一次新的造訪」</span>設定。 </p> </p> <p> <p>注意: 如果您已在管理控制台中停用背景點擊的舊版處理功能，則此類點擊將不會在父報表套裝中顯示，而會在虛擬報表套裝中出現。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>如果我必須追蹤背景點擊，需要使用哪個 SDK 版本?</b> </td> 
   <td colname="col2"> <p> 您必須使用 SDK 4.13.6 版或更高版本。 </p> </td> 
  </tr> 
 </tbody> 
</table>


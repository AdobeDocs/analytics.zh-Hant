---
description: 回答實作 Audience Analytics 時可能遇到的問題。
seo-description: 回答實作 Audience Analytics 時可能遇到的問題。
seo-title: 常見問題集
solution: Experience Cloud
title: 常見問題集
uuid: 9dfc8f19-f9b2-4c2e-bff9-3d91cfe01bca
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# 常見問題集

回答實作 Audience Analytics 時可能遇到的問題。

## 法律常見問題 {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>問: 如何知道我的 Analytics 資料中是否有個人識別資訊 (PII)? 如果有，我該怎麼做?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">如果您的 prop 或 eVar 中有電子郵件/地址等資訊，請考慮在收集時將這些資訊進行雜湊處理。 </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">如果您的國家/地區認為 IP 位址是 PII，請<a href="https://marketing.adobe.com/resources/help/en_US/reference/exclude_IP.html"  >開啟 IP 模糊化</a>功能。 </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">請與您的 Analytics 管理員討論，了解您正在收集哪些資訊。 </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">與您的法律部門討論，了解他們認為哪些資訊屬於 PII。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>問: 如何知道我的報表套裝是進行站上個人化，還是離站/站上鎖定?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">這些不適用於傳送Adobe Analytics資料至Adobe Audience Manager。 </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">請自問: 您是否會將 Analytics 共用區段與 Experience Cloud 中的 MCA 維度共用? </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">您是否匯出 (例如透過資料饋送) 至用於這些目的的商業智慧 (BI) 系統? </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## AAM 專屬常見問題 {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>問: 如何在 Audience Manager 中建立 Analytics 目標?</b> </p> </td> 
   <td colname="col2"> 請參 <a href="https://marketing.adobe.com/resources/help/en_US/aam/create-analytics-destination.html"  > 閱在AAM中設定Analytics目標 </a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 建立並儲存 Analytics 目標後，需要多久才會在我選取的表套裝中顯示資料?</b> </p> </td> 
   <td colname="col2"> <p>將新資料填入您的報表套裝可能需要數小時。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 我已建立了一個新 Analytics 目標，但在可用區段的「目標對應」區段中看不到。這個目標在哪裡，我要如何找到它?</b> </p> </td> 
   <td colname="col2"> <p>當您在<span class="uicontrol">「區段對應」</span>中選取<span class="uicontrol">「自動對應所有目前和未來的區段」</span>選項時，Analytics 目標會從區段的「目標對應」區段消失。 </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>要防止此情況，請選取<span class="uicontrol">「手動對應區段」</span>來取代自動選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>問：這是否能提供Analytics中AAM的所有資訊？</b> </p> </td> 
   <td colname="col2"> <p>否，只限在啟用 Audience Manager 對象期間或之後以及在符合區段資格期間或之後造訪您網站之使用者的相關資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>問: 這可提供每個區段的可定址對象總數嗎?</b> </p> </td> 
   <td colname="col2"> <p>不一定。您可得知在符合區段資格期間或之後來到您網站的該區段訪客數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>問: 這跟連到 Analytics 的舊版 Cookie 目的地有何不同?</b> </p> </td> 
   <td colname="col2"> <p>區段符合資格並即時傳回——在相同點擊上。 </p> <p>系統會自動顯示易記名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 如果我的某些報表套裝載有個人資料，而其他沒有，該怎麼辦?</b> </p> </td> 
   <td colname="col2"> <p>提示: 建立兩個目標──將個人資料報表套裝新增至一個目標，並將沒有個人資料的報表套裝新增至另一個目標。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics 專屬常見問題 {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>問: 此整合在 Analytics 中會以維度還是區段形式顯示?</b> </p> </td> 
   <td colname="col2"> <p>以維度形式:「適用對象 ID」和「對象名稱」。實施流量分類。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 在 Analytics 中，可以在哪裡使用這些維度?</b> </p> </td> 
   <td colname="col2"> <p>幾乎所有位置; 這些維度的處理方式與在 Analytics 中收集的任何其他維度相同。但有兩項例外: 資料目前不會出現在 Data Workbench 或 Livestream 中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問：為何我不看到Analytics中的資料流傳？</b> </p> </td> 
   <td colname="col2"> <p>您可能在資料來源與目的地之間有衝突的AAM隱私權控制。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 即使我已選擇傳送所有區段，為何在 Analytics 中仍會遺失部分區段?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">您的AAM資料匯出控制項在目標和區段資料來源中可能會發生衝突，導致某些區段無法傳送。 </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">若您在區段中使用了第三方資料特徵，則這些區段無法與包含個人資料的目標 (一組報表套裝) 共用。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問：我為何在Analytics報表中看到「已達對象限制」? (注意：這也會在資料倉庫中顯示為「對象ID = -1」和「:::max_audiences_exceeded::」)</b> </p> </td> 
   <td colname="col2"> <p>依預設，AAM 的 Audience Analytics 整合會將訪客符合條件的所有區段，按每次點擊傳送到 Analytics。如果某位訪客在一次點擊中所屬的 AAM 區段超過 150 個，則最新的 <b>150 個合格區段</b>會傳送到 Analytics，而其餘的清單會被截斷。 </p> <p>會傳送其他標幟給Analytics，表示區段清單已截斷，並在「對象名稱」維度中顯示為「已達對象限制」，在「對象ID」維度中顯示為「-1」。 </p> <p>雖然訪客不太可能在特定的點擊中符合超過 150 個區段，但偶然情況下也可能會發生。如果您在報告中遇到「已達受眾限制」，您有兩個選項： </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>選項　１</b>: 繼續讓整合工作以立即可用狀態作業，針對特定訪客傳送最新的 150 個合格區段。 </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>選項 2</b>: 在 AAM 中，選擇對您業務而言最重要的 150 個區段進行整合。AAM 隨即根據這 150 個區段檢查訪客。此方法的缺點是，在所有訪客中，您僅能收到這 150 個區段。換句話說，由於整合的按點擊性質，「選項 1」方法可以提供無限區段。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 為了進行整合，Analytics 是否需要為額外的伺服器呼叫付費?</b> </p> </td> 
   <td colname="col2"> <p>否。AAM Audiences 已納入 Analytics 點擊伺服器端。這不會導致 Analytics (主要或次要) 的額外伺服器呼叫。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 伺服器端轉送 (SSF) 常見問題 {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>問: 如果我已實作舊式 SSF，我是否還需要前往 Analytics「管理控制台」並開啟報表套裝 SSF?</b> </p> </td> 
   <td colname="col2"> <p>是。在 AAM 目標設定中，您只會看見已開啟 SSF 的報表套裝。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問：為什麼無法在Analytics管理員中為SSF開啟特定報表套裝？</b> </p> </td> 
   <td colname="col2"> <p>只能啟用對應至您Experience cloud組織的套裝。 </p> </td> 
  </tr> 
 </tbody> 
</table>

如需有關此主題的更多常見問答集，請 [參閱伺服器端轉送常見問答集](/help/admin/admin/c-server-side-forwarding/ssf-faq.md)。

## 一般常見問題 {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>問: 為何 Audience Manager 和 Analytics 之間的區段訪客計數不一樣?</b> </p> </td> 
   <td colname="col2"> <p>請參閱 <a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  > 訪客計數差異 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: AAM 中的「對象」與 Analytics 中的「區段」有何不同?</b> </p> </td> 
   <td colname="col2"> <p>請參閱 <a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > Understand Segments in Analytics and Audience Manager </a>. </p> <p>AAM 對象會傳送出去並以「維度」元件形式共用，以供 Analytics 使用。例如，它們不會在「區段產生器」中以區段顯示，而是可以用來建立區段的維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 從 AAM 整合的「客戶屬性」和客戶資料有何不同?</b> </p> </td> 
   <td colname="col2"> <p>「客戶屬性」不是以時間為基礎; 可回溯和往前套用。AAM 整合的資料則是以時間為基礎並僅可往前。此外，「客戶屬性」是 Experience Cloud 訪客 ID 的查找表格，而 AAM 整合是拼接到訪客每個點擊中的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 有何針對此問題的舊版方法，例如舊的測試版或「諮詢」外掛程式 Cookie 目標?</b> </p> </td> 
   <td colname="col2"> <p>我們建議您實作新的整合，並刪除舊目標。 </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: 有關 Advertising Analytics 的常見問題集。
title: Advertising Analytics 的常見問題集
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 591b82e271cc7474e9b413015804d4fe37d9050c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 51%

---

# 常見問答

## 存取/權益 {#access}

+++ 我需要是Adobe Advertising Cloud或Adobe Advertising Cloud (AMO)客戶才能存取這項功能嗎？

否，此功能適用於非Advertising Cloud和非AMO客戶。 </p> <p>AMO 客戶能運用現有的 Analytics-AMO 整合，因此不需要使用 Ad Analytics。

+++

+++ 哪些Adobe Analytics SKU授予您使用Advertising Analytics的權益？

Advertising Analytics適用於Adobe Analytics

* [選取](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/prime.html)

* [Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/ultimate.html)

+++

+++ 使用Advertising Analytics需要額外付費嗎？

不需要，除了適當的SKU布建，Advertising Analytics不需要額外付費。

+++

+++ Advertising Analytics是否會計入我的伺服器呼叫使用量

否，Advertising Analytics使用特殊的資料來源型別，因此不會產生伺服器呼叫成本。

+++

+++ 如果我已經使用Advertising Cloud/AMO，還可以使用Advertising Analytics功能嗎？

任何相容的搜尋引擎帳戶都會傳入Advertising Analytics，並顯示為唯讀。 所有編輯或更新作業都應該在 Advertising Cloud/AMO 中處理。

+++

+++ 我擁有正確的SKU，但無法存取Advertising Analytics，為什麼？

Advertising Analytics僅適用於Adobe Analytics管理員，不過管理員可以向非管理員授予存取權。 如需存取權限，請聯絡您的管理員。

+++

## 使用 Advertising Analytics {#using}

+++ Advertising Analytics包含哪些搜尋引擎帳戶？

搜尋引擎帳戶包括Google AdWords和Microsoft Bing。

+++

+++ 若要存取Advertising Analytics，我該前往何處？

登入Adobe Analytics後，導覽至 [!UICONTROL 管理員]. 然後選取 [!UICONTROL Advertising Analytics] 以新增您的搜尋引擎帳戶。

+++

+++ 資料收集和傳遞至Analytics的方式為何？

Advertising Analytics運用一系列自訂API，透過Adobe Advertising Cloud將資料從搜尋引擎傳遞至Analytics。

+++

+++ 這項整合能提供給我哪些搜尋資料？

您將獲得

* 曝光數
* 點擊數
* 成本
* 品質分數
* 直接來自搜尋引擎的平均位置，以及
* AMO ID例項（按一下「例項」）。

+++

+++ 我可以根據其他Advertising Analytics資料（量度/維度）劃分Analytics資料嗎？

否，原始搜尋資料將以獨立資料集的形式提供。 不過，您可以根據其他 Analytics 資料劃分實例版本的點選資料。

+++ 帳戶中各種狀態指標（擱置中、作用中、已暫停等）的定義是什麼？ 這些狀態指標中的每一項都可識別每個搜尋引擎帳戶的生命週期階段。

* [!UICONTROL 擱置中]
* [!UICONTROL 已暫停]表示帳戶先前已設定，但目前處於非作用中狀態。
* [!UICONTROL 作用中]表示帳戶已完全設定，而且正在提取搜尋資料。

+++

+++ 我正在嘗試將我的Advertising Analytics帳戶對應到特定的報表套裝，不過在報表套裝強制回應中找不到帳戶。 原因為何？

將報表套裝指派至Advertising Analytics帳戶前，您需要先執行下列動作：指派所需的報表套裝 [已針對Advertising Analytics報告進行布建](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
您可以透過個別的「管理員」頁面完成指派作業，請前往： 「管理員>報表套裝> 」 [選取報表套裝] >編輯設定> Advertising Analytics設定。

+++

+++ 是否可以將虛擬報表套裝指派至Advertising Analytics帳戶？

虛擬報表套裝不會收集資料，因此您無法直接將Advertising Analytics帳戶對應至虛擬報表套裝。 不過，您可以將Advertising Analytics帳戶對應至您想要在其中檢視資料的虛擬報表套裝的父報表套裝。 搜尋引擎量度（點選次數/成本/曝光數）可能不會顯示在虛擬報表套裝中，除非您在以AMO ID （或其分類）為基礎的區段邏輯中加入「或」條件。 例如：新增「有 AMO ID 的所有點擊」後，區段中就會包含搜尋引擎量度。

+++

+++ Advertising Analytics量度是否可報告於 <b>行銷管道</b> 報告？

不可以，行銷管道報表不含這些度量。

+++

+++ 系統會在什麼時候將搜尋資料提取至 Analytics?

系統從搜尋引擎提取搜尋資料的時間，大約是在您所屬 Analytics 資料中心當地時區的上午 6 點 (06:00)。這也是收集 AMO 資料並將其插入報表套裝的時間。 該資料接著會在資料插入 Analytics 的過程中轉換為報表套裝的時區。

+++

+++ 什麼可以是 <b>已擷取點選前</b>？ 我們是否在未點擊前就帶來了曝光數、成本、平均位置等資料？ </p> </td>

AMO ID會擷取搜尋引擎量度：曝光數、成本、點按數、平均位置和平均品質分數。 如果沒有點擊次數，但是有曝光次數，則曝光數/位置/品質分數仍然會傳送到 Analytics。一般來說，如果沒有點擊數，也就不會有成本。

+++

+++ 會在哪個層級擷取此資料？ <b>訪客？點擊？</b>

搜尋引擎量度會在點選層級擷取，並連結至AMO ID （及其分類）。 這是屬於摘要層級資料，不會連結至造訪/訪客。因此，搜尋引擎量度只能用在屬於點擊層級範圍並且是以 AMO ID (而非其分類) 為基礎的區段。

AMO ID 也會在點擊登陸頁面時在該頁面擷取 (連結至造訪/訪客)，而且持續的下游行為會為其他 Analytics 量度取得分數 (直到該 AMO ID 過期或是由新的 AMO ID 覆寫為止)。它會像其他 eVar 一樣完全整合到資料集中。

+++

+++ 我們是隻擷取google.com還是 <b>國家/地區版本</b> (例如google.co.uk、google.it、google.fr或google.de)也一樣？

「廣告平台」分類會擷取「Google Adwords」和「Bing Ads」等值。 常用的最佳作法就是將國碼納入行銷活動命名的一部分。接著，您就可以往下篩選或區隔 (例如，如果所有的行銷活動是以 countrycode_ 開頭，您可建立一個區段，讓其中的行銷活動 (AMO ID) 是以「UK_」為開頭，就能取得英國的資料)。

+++

+++ 「AMO成本」量度是按照搜尋引擎的報告為每個關鍵字/廣告支付的成本。 這是淨成本或總成本？

「AMO成本」僅為支付給搜尋引擎的成本。 不包括任何廣告商或搜尋最佳化/管理平台費用。

+++

+++ 是否有包括其他廣告管道的計畫，例如 <b>顯示</b> 或 <b>社交</b>？

否，目前我們在藍圖中沒有針對這些其他管道的計畫。

+++


## 自動與手動追蹤 {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>問：在設定 Advertising 帳戶時，系統指出<b>自動追蹤</b>可能會產生非預期的結果。可能會發生哪幾種結果？ </p> </td> 
   <td colname="col2"> <p>答： 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">自動模式會嘗試以正確格式將 URL 參數附加到追蹤範本/目的地 URL 的結尾。<b>儘管如此，您還是必須負責確認新增的 URL 參數正確無誤，才能順利前往最終的登陸頁面。</b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">自動模式能將關鍵字插入登陸 URL，不過網站伺服器可能不支援含特殊字元的關鍵字。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>問：若一開始設定了手動或自動追蹤，稍後<b>可以切換</b>至另一個追蹤模式嗎？有什麼影響？ </p> </td> 
   <td colname="col2"> <p>答：可以切換，但在切換之前需要先移除舊的追蹤邏輯。這可能導致切換當天的追蹤中斷 (特別是從手動切換至自動的情況)。因此，除非絕對必要，否則建議不要進行切換。 </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>從手動切換至自動</b>：移除追蹤範本的手動新增項目，然後在 Advertising Analytics 使用者介面中，從手動切換至自動並儲存設定。請注意，系統可能需要花費長達數小時以填入自動追蹤代碼。 </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>從自動切換至手動</b>：在 Advertising Analytics 設定使用者介面中，從自動切換至手動，然後盡可能快速地部署手動追蹤代碼。部署手動追蹤代碼時，若在搜尋引擎追蹤範本中看到自動追蹤代碼，請將其移除。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

---
description: 此參考表格定義您可以在「行銷渠道處理規則」頁面上選取的欄位、選項和點按屬性。
subtopic: Marketing channels
title: 行銷渠道處理規則 - 定義
topic: Reports and analytics
uuid: 4e71ff5b-912a-4dc0-9c22-4be74c5e3cc0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 行銷渠道處理規則 - 定義

此參考表格定義您可以在「行銷渠道處理規則」頁面上選取的欄位、選項和點按屬性。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>術語 </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>全部 </p> </td> 
   <td colname="col2"> <p>僅當編號規則中的全部規則均為 true 時，啟用該渠道。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>任何 </p> </td> 
   <td colname="col2"> <p>當規則集中的任何規則為 true 時，啟用該渠道。該選項僅當編號規則中存在多個規則時方可用。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p>Advertising Cloud 與 Advertising Analytics 整合所使用的主要追蹤程式碼。當其中一項整合啟用時，追蹤程式碼首碼可用來識別 Advertising Cloud 專用的管道。「AMO ID」的開頭使用「AL」代表 Search，「AC」代表 Display，「AO」則代表 Social。行銷管道中使用 AMO ID 時，點按/成本/曝光量度可歸因為正確的管道 (若未設定，這些量度將變為「直接」或「無」)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ED ID </p> </td> 
   <td colname="col2"> <p>Advertising Cloud 使用的次要追蹤程式碼。此追蹤程式碼的主要用途是作為將資料傳回 Ad Cloud 的金鑰。不過，如果您想要將 ClickThroughs 和 ViewThroughs 視為兩個不同的行銷管道，也可以用它來識別 Display ClickThroughs 與 Display ViewThroughs。方法是為以「:d」結尾 (代表 Display ClickThroughs) 或結尾為「:i」(代表 Display ViewThroughs) 的「AMO EF ID」設定行銷管道邏輯。如果您不想將 Display 分割為兩個管道，請改用 AMO ID 維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>轉換變數 </p> </td> 
   <td colname="col2"> <p>包含為該報表套裝啟用的 eVar，並僅當透過頁面上的 Adobe 代碼設定這些變數時套用。 </p> <p>請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf"  > 實施指南</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>存在 </p> </td> 
   <td colname="col2"> <p>具備多個可用選擇，包括: </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol">不存在</span>: 指定請求上並不存在點按屬性。例如，在反向連結網域中，如果使用者輸入 URL 或按一下書籤，反向連結網域屬性並不存在。 </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol">為空</span>: 指定點按屬性存在，通常為 eVar 或查詢字串參數，但沒有與點按屬性相關的值。 </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol">不包含</span>: 例如讓您指定某反向連結網域不包含特定值 (與使用<span class="term">包含</span>選項相反)。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將該渠道識別為 </p> </td> 
   <td colname="col2"> <p>將規則與新增至<span class="wintitle">行銷渠道管理員</span>頁面的行銷渠道相關聯。 </p> <p>請參閱<a href="/help/components/c-marketing-channels/c-channels.md"   >新增行銷管道</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>匹配付費搜尋的偵測規則 </p> </td> 
   <td colname="col2"> <p>Adobe 偵測的付費搜尋。付費搜尋是指公司付款以將其網站列入搜尋引擎。付費搜尋通常顯示在搜尋結果的頂部或右側。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>匹配免費搜尋的偵測規則 </p> </td> 
   <td colname="col2"> <p>Adobe 報表偵測的免費搜尋。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結匹配內部 URL 篩選器 </p> </td> 
   <td colname="col2"> <p> 瀏覽的頁面 URL 與內部 URL 篩選器匹配，該內部 URL 篩選器是為「管理工具」的報表套裝而定義的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結不匹配內部 URL 篩選器 </p> </td> 
   <td colname="col2"> <p>反向連結 URL 與一個內部 URL 篩選器不相符，並且這是為「管理工具」的報表套裝而定義的。此設定可搭配使用<span class="term">頁面 URL </span> 和<span class="term">存在</span>來設定範圍廣泛的規則，如此一來就不會有任何造訪落在報表的<a href="/help/components/c-marketing-channels/c-faq.md#no-channel-identified" >未識別管道</a>區段中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>忽略符合內部 URL 篩選條件的點按 </p> </td> 
   <td colname="col2"> <p>(適用於反向連結) 僅跟蹤來自外部反向連結網站的點按。通常，除非您想要包含內部流量，否則此設定保留啟用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>是第一個瀏覽的頁面 </p> </td> 
   <td colname="col2"> <p>由 Adobe 報表偵測到的瀏覽首頁。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面 </p> </td> 
   <td colname="col2"> <p>您網站上使用 Adobe 網站信標所標記的網頁之頁面名稱。此值等同於 <span class="varname"> s.pageName </span>。範例包括<span class="varname">首頁</span>和<span class="varname">關於我們</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面網域 </p> </td> 
   <td colname="col2"> <p>訪客著陸的頁面網域，例如 <span class="filepath">products.example.co.uk</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面網域和路徑 </p> </td> 
   <td colname="col2"> <p>網域和路徑，例如 <span class="filepath">products.example.co.uk/mens/pants/overview.html</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面根網域 (TLD+1) </p> </td> 
   <td colname="col2"> <p>訪客著陸的頁面根網域，例如 <span class="filepath">example.co.uk</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面 URL </p> </td> 
   <td colname="col2"> <p>您網站某個網頁的 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結網域 </p> </td> 
   <td colname="col2"> <p>訪客在瀏覽您的網站前所處的網域，例如，源自 <span class="filepath">abcsite.com</span> 與 <span class="filepath">xyzsite.com</span> 的反向連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查詢字串參數 </p> </td> 
   <td colname="col2"> <p>如果網頁 URL 類似於 <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>，則 page 和 cat 均為查詢字串參數。(請參閱 <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>。) </p> <p>您可為每個規則集僅指定一個查詢字串參數。若要新增其他查詢字串參數，請使用 <span class="uicontrol">ANY</span> 作為運算元，然後新增查詢字串參數至此規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結 </p> </td> 
   <td colname="col2"> <p>訪客在來到您網站之前所處的網頁位置 (完整 URL)。反向連結存在於您所定義網域之外。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結網域和路徑 </p> </td> 
   <td colname="col2"> <p>反向連結網域和 URL 路徑的串連例如:  </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結參數 </p> </td> 
   <td colname="col2"> <p>反向連結 URL 上的查詢字串參數。例如，如果訪客來自 <span class="filepath">example.com/?page=12345&amp;cat=1</span>，則 page 和 cat 為反向連結參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反向連結根網域 </p> </td> 
   <td colname="col2"> <p>反向連結的根網域。反向連結存在於您所定義網域之外。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜尋引擎 </p> </td> 
   <td colname="col2"> <p>類似 Google 或 Yahoo! 將訪客帶至您網站的搜尋引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜尋關鍵字 </p> </td> 
   <td colname="col2"> <p>使用搜尋引擎來執行搜尋的一個詞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜尋引擎 + 關鍵字 </p> </td> 
   <td colname="col2"> <p>搜尋關鍵字和搜尋引擎的串連，以唯一識別搜尋引擎。例如，如果搜尋 computer，則搜尋引擎和關鍵字的識別如下所示: </p> 
    <code>
      Search&nbsp;Tracking&nbsp;Code&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"&lt;search_type&gt;:&lt;search&nbsp;engine&gt;:&lt;search&nbsp;keyword&gt;"&nbsp;where &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;search_type&nbsp;=&nbsp;"n"&nbsp;or&nbsp;"p",&nbsp;search_engine&nbsp;=&nbsp;"Google",&nbsp;and&nbsp;search_keyword&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"computer" 
    </code> <p><b>注意:</b> n = 免費; p = 付費 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定該渠道的值為 </p> </td> 
   <td colname="col2"> <p>除了瞭解為您網站帶來訪客的行銷管道之外，您還能知道管道內的哪些橫幅廣告、搜尋關鍵字或電子郵件促銷活動為訪客的網站活動獲得評分。該 ID 是與渠道一同儲存的渠道值。該值通常為內嵌於著陸頁面或反向連結 URL 中的促銷活動 ID，有時也是搜尋引擎和搜尋關鍵字組合，或是最近識別特定渠道中訪客的反向連結 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>

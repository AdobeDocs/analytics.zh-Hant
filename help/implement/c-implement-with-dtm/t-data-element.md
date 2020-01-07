---
description: 在動態標籤管理中建立資料元素。
keywords: Dynamic Tag Management;data element;create new data element;name;type;default value;force lowercase value;remember this value for
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 建立資料元素
uuid: eacd5c60-6197-4129-a9e1-a39e9a58b38a
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 建立資料元素

在動態標籤管理中建立資料元素。

1. [建立 Web 屬性](/help/implement/c-implement-with-dtm/t-create-web-property.md) (如果尚未這麼做的話)。
1. 在 Web 屬性中，按一下&#x200B;**[!UICONTROL 規則]** &gt; **[!UICONTROL 資料元素]**。
1. 按一下&#x200B;**[!UICONTROL 「建立新資料元素」]**。
1. 填入下列欄位和選項:

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> 選項</th> 
      <th class="chdeschd"> 說明</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>名稱</strong></td> 
      <td class="chdesc stentry"> <p>行銷人員看得懂的資料元素易記名稱。例如, 
        <code>
          Product ID
        </code>. </p> <p> <p>注意: 規則產生器會參考名稱，而不是 ID。如果您變更資料元素的名稱，您必須在使用該元素的每個規則中變更其參考。 </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>類型</strong></td> 
      <td class="chdesc stentry"> <p> 指定提取資料的來源，例如 JS 物件、CSS 選擇器、Cookie、URL 參數或自訂指令檔。 </p> <p>視您選取的類型而定，會顯示不同的選項。如需詳細資訊與範例，請參閱動態標籤管理產品文件中的<a href="https://marketing.adobe.com/resources/help/zh_TW/dtm/data_elements.html">資料元素類型</a>。 </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>預設值</strong></td> 
      <td class="chdesc stentry"> <p>預設元素。即使 URL 參數不存在或動態標籤管理找不到 URL 參數，此值可確保資料元素總是有值。 </p> <p> <p>注意: 如果沒有值和沒有預設值，則不會傳回任何項目。不會設定參考該資料元素的任何變數。也請注意，如果它是「自訂代碼」資料元素，即會忽略預設值欄位。 </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>強制小寫值</strong></td> 
      <td class="chdesc stentry"> <p>動態標籤管理會自動使值變成小寫。 </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>記住此值</strong></td> 
      <td class="chdesc stentry"> <p>您想要動態標籤管理記住此值多久的時間。 </p> <p> 有效值包括: </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>作業階段: 以作業階段為基礎的計時會依實施而有所差異。作業階段資料元素會設為作業階段 Cookie。不過，此設定會視網站伺服器或瀏覽器而定。它和行銷報表與分析中所用的作業階段無關。 </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>頁面檢視 </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>訪客 </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   如需有關如何使用資料元素的詳細資訊，請參閱 Adobe 標籤管理產品文件中的[資料元素](https://marketing.adobe.com/resources/help/zh_TW/dtm/data_elements.html)。
1. 按一下&#x200B;**[!UICONTROL 儲存資料元素]**。

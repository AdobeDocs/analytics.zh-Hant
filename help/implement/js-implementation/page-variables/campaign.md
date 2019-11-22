---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---



# campaign

 變數可識別用以吸引訪客進入網站的促銷活動。的值通常取自查詢字串參數。https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables/browserheight.html

<!-- 

campaign.xml

 -->

**參數**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 位元組 </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>轉換 &gt; 促銷活動 &gt; 追蹤代碼 </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

促銷活動中的每個元素都應有一個相關聯的唯一追蹤代碼。例如，付費搜尋引擎關鍵字的追蹤代碼可能是 112233。當某人按一下追蹤代碼為 112233 的關鍵字時，將會被導向至對應的網站，而  *`campaign`*&#x200B;變數會記錄該追蹤代碼。

有兩種主要方法可填入 *`campaign`* 變數:

* [!UICONTROL getQueryParam] 外掛程式，用於 JavaScript 檔案，可從 URL 中擷取查詢字串參數。如需 [!UICONTROL getQueryParam] 外掛程式的詳細資訊，請參閱[實施外掛程式](/help/implement/js-implementation/plugins/impl-plugins.md).

* 將值指派給網頁的 HTML 中的 *`campaign`* 變數。

使用其中一個填入 *`campaign`* 變數的方法後，返回按鈕流量可能會使來自促銷活動元素的實際點進次數膨脹。

例如，假設某個訪客在點選付費搜尋關鍵字後進入了您的網站。當訪客進入登陸頁面時，URL 會包含一個查詢字串參數，識別該關鍵字的追蹤代碼。接著，訪客點選了其他頁面的連結，但隨即又點選了「上一頁」按鈕，而返回登陸頁面。當訪客第二次進入登陸頁面時，含有查詢字串參數的 URL 會再次識別追蹤代碼。第二次點進也會註冊，而使點進次數不實膨脹。

為避免點進次數因此而膨脹，Adobe 建議您使用 [!UICONTROL getValOnce] 外掛程式，強制每個促銷活動點進在一個工作階段中僅計數一次。如需 [!UICONTROL getValOnce] 外掛程式的詳細資訊，請參閱[實施外掛程式](/help/implement/js-implementation/plugins/impl-plugins.md).

**語法和可能的值** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

*`campaign`* 變數具有與其他所有變數相同的限制。Adobe 建議您將值限定為標準 ASCII 字元。

**區分大小寫** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

eVar 不區分大小寫，但會以第一次出現時的大寫格式顯示。例如，若 eVar1 的第一個例項設為 "Logged In"，但後續所有的例項皆以 "logged in" 的格式傳入，則報表一律會將 eVar 的值顯示為 "Logged In"。

**範例** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**組態設定** {#section_4083F281968443169EAF8C0E8529D7BC}

每個促銷活動值在過期之前都會對使用者起作用，且會因為該使用者的活動和成功事件而獲得評價。您可以在「管理控制台」中變更促銷活動變數的到期日。

**缺陷、問題和提示** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* 若要避免點進次數不實膨脹，請使用 [!UICONTROL getValOnce] 外掛程式，使每個促銷活動點進在一個工作階段中僅計數一次。如需 [!UICONTROL getValOnce] 外掛程式的詳細資訊，請參閱[實施外掛程式](/help/implement/js-implementation/plugins/impl-plugins.md).

* 如需追蹤促銷活動和關鍵字購買的詳細資訊，請參閱[促銷活動](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html)。
* 使用 [!DNL DigitalPulse Debugger] 可檢視促銷活動的實際值 (除錯程式中的 v0)。若除錯程式中未出現 v0，表示對於該頁面未記錄任何促銷活動資料。

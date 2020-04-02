---
description: 本節適用對象為 Adobe Analytics 系統管理員。本節重點放在新的連結追蹤參數，以及這些新參數如何在瀏覽器和裝置之間確保連結獨特性和一致性，並改善頁面上的連結重新定位處理。
title: 連結追蹤方法
topic: Activity map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
translation-type: ht
source-git-commit: abf808e956ca78c9e7ceaa5240d4e1ea20f90aec

---


# 連結追蹤方法

本節適用對象為 Adobe Analytics 系統管理員。本節重點放在新的連結追蹤參數，以及這些新參數如何在瀏覽器和裝置之間確保連結獨特性和一致性，並改善頁面上的連結重新定位處理。

>[!IMPORTANT]
>
>任何可能含有 PII (個人識別資訊) 之文字的連結，都應使用 [s_objectID](https://marketing.adobe.com/resources/help/zh_TW/sc/implement/s_objectID.html) 明確實作，或是使用 [s.ActivityMap.linkExclusions 或 s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars) 排除 ActivityMap 連結集合。如需進一步瞭解 Activity Map 收集 PII 資料的可能方式，請前往[這裡](/help/analyze/activity-map/lnk-tracking-overview.md)。

Activity Map 的連結追蹤是根據下列兩個 ID：

* 主要 ID：這是連結的可識別參數。
* 連結地區：這是次要參數，可讓使用者指定該頁面或地區中整體連結區域的代表字串。如果使用者未提供此參數，此參數可以自動產生。

## 主要 ID{#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

如果 HTML 有 s_objectid，則主要 ID 預設為 s_objectid。否則會使用下列參數做為主要 ID (按照下列優先順序)：

* Innertext
* Alttext
* 標題
* Src
* Action

## 使用 InnerText 和使用連結動作 (URL) 的比較{#section_70C3573E22274522A8CC035BF18EC468}

「連結動作」是當連結被點按時，網頁所採取的動作 - 通常是連結點按後造訪的 URL。使用連結動作時可能會遇到的問題包括：

* 兩個以上不同的連結具有相同 ID
* 連結的可讀性
* 單一連結具有多重動作 (取決於您用於檢視連結的裝置)

因此，我們改用 InnerText，比起連結動作 (URL) 具有以下優點：

* 可以良好表示連結身份。可以大幅降低主要 ID 重複項目，因為不常發生多個連結具有相同文字。
* 可確保主要 ID 在所有裝置和瀏覽器類型間保持一致性。
* 不受頁面上連結重新定位的影響。
* 改善可讀性，讓使用者可以在 Activity Map 外部分析連結追蹤報表。

## 連結地區 {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

這個新屬性可讓使用者指定字串，用來代表連結所在的頁面地區。

例如，針對位在網頁之功能表區段的「聯絡我們」連結，使用者可能會想傳遞「功能表」(Menu) 地區參數。同樣地，對於位在網頁頁尾的「聯絡我們」連結，地區參數可以設為「頁尾」(footer)。

連結地區值並非設在連結本身，而是設在包含該地區的 DOM HTML 樹狀結構上的一個 HTML 元素中。使用「連結地區」具備下列優點：

* 可協助區分具相同主要 ID 的連結。
* 地區趨勢分析較不受網頁的動態方面影響。
* 使用者可查看某地區內績效最佳的連結。使用地區做為錨記，可以顯示頁面中目前隱藏之連結的覆蓋圖 (Ajax、鎖定)。
* 由於特定地區可在許多網頁間使用，因此地區可以取代頁面。這可協助回答類似下列問題：「我的『產品供應』地區在女性登陸頁面還是男性登陸頁面表現最佳？
* 地區本身是相關維度，可分析高度動態網頁。這是因為它可移除不斷變動連結所造成的雜訊：例如，CNN 登陸頁面中的「最新消息」地區可能會有很多變動連結。但地區永遠存在。所以在地區層級針對許多天進行分析，應該可獲得有趣的結果。

**自訂地區追蹤**

您可以自訂連結的地區參數 (預設為連結 ID)：設為 &quot;ID&quot; 的標記會使用具有 &quot;id&quot; 參數的所有 HTML 元素做為「地區」。因此，將地區標記設為 &quot;id&quot; 最有可能傳回許多不同的地區 (數量即頁面上設定的 &quot;ID&quot; 數)。此外，如果您想要自訂性更強的實作，可將地區標記設定為更具體的項目，例如 &quot;region_id&quot;。

以下顯示一些使用預設地區 ID 屬性 &quot;id&quot; 的 HTML 範例。

```
<div id="content"> 
  <div id="breaking_news"> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
```

您也可使用任意字串識別碼 (以下範例中為 &quot;lpos&quot;) 來標記元素，接著使用名稱 &quot;lpos&quot; 新增屬性。

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute="lpos";
</script> 
   
<div id="nav" lpos="navbar"> 
  <ul> 
     <li> Menu Category A 
    <ul> 
      <li><a href="">Menu Item A 1</a> 
      <li><a href="">Menu Item A 2</a> 
     </ul> 
    </li> 
     <li> Menu Category B 
     <ul> 
      <li><a href="">Menu Item B 1</a>  
      <li><a href="">Menu Item B 2</a> 
  
   </ul> 
</ul> 
</div> 
  
<div id="content" > 
  <div id="breaking_news" lpos="breaking_news> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
</div>
```

## 設定變數 {#configuration-vars}

請注意，以下所列變數僅供參考。Activity Map 在出廠時即已正確設定，但您可使用這些變數來自訂實作。

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數名稱 </th> 
   <th colname="col2" class="entry"> 範例 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionIDAttribute </td> 
   <td colname="col2"> 預設為 "id" 參數。您可將此變數設定為其他參數。 </td> 
   <td colname="col3"> 字串，用來識別 s.linkObject 的某些上階 (parent、parent.parent 等) 元素 (亦即<b>被點按的元素</b>) 中，做為地區 ID 的標記屬性。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;linkId; &nbsp;&nbsp;&nbsp;if(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A'){ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title'); &nbsp;&nbsp;&nbsp;} &nbsp;&nbsp;&nbsp;return&nbsp;linkId; } 
    </code> </td> 
   <td colname="col3"> 函數，接受被點按的 HTMLElement，且應傳回代表<b>被點按的連結</b>的字串值。 <p>如果傳回值為 false (null、未定義、空字串、0)，將不會追蹤任何連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;regionId,className; &nbsp;&nbsp;&nbsp;while(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement=&nbsp;clickedElement.parentNode)){ &nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName; &nbsp;if(regionId){ &nbsp;return&nbsp;regionId.toLowerCase(); &nbsp;} &nbsp;} } 
    </code> </td> 
   <td colname="col3"> 函數，接受被點按的 HTMLElement，且應傳回代表<b>在點按時連結所在地區</b>的字串值。 <p>如果傳回值為 false (null、未定義、空字串、0)，將不會追蹤任何連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class &nbsp;&lt;style&gt; .linkExcluded{ &nbsp;&nbsp;display:&nbsp;block; &nbsp;&nbsp;height:&nbsp;1px; &nbsp;&nbsp;left:&nbsp;-9999px; &nbsp;&nbsp;overflow:&nbsp;hidden; &nbsp;&nbsp;position:&nbsp;absolute; &nbsp;&nbsp;width:&nbsp;1px; } &lt;/style&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;&lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt; &lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>接受以逗號分隔的字串清單以在連結文字中進行尋找的字串若找到，則該連結排除由 Activity Map 追蹤。若未設定，則 Activity Map 並未試圖停止追蹤該連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap &lt;div&nbsp;id="links-included"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;div&nbsp;id="links-excluded"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>接受以逗號分隔的字串清單以在地區文字中進行尋找的字串。若找到，則該連結排除由 Activity Map 追蹤。若未設定，則 Activity Map 並未試圖停止追蹤該連結。 </p> </td> 
  </tr> 
 </tbody> 
</table>

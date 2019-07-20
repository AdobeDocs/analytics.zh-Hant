---
description: 本節適用對象為 Adobe Analytics 系統管理員。本節重點放在新的連結追蹤參數，以及這些新參數如何在瀏覽器和裝置之間確保連結獨特性和一致性，並改善頁面上的連結重新定位處理。
seo-description: 本節適用對象為 Adobe Analytics 系統管理員。本節重點放在新的連結追蹤參數，以及這些新參數如何在瀏覽器和裝置之間確保連結獨特性和一致性，並改善頁面上的連結重新定位處理。
seo-title: 連結追蹤方法
solution: Analytics
title: 連結追蹤方法
topic: Activity Map
uuid: 67864fb9-33cd-46fa-89a8-4d83d83d
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# 連結追蹤方法

本節適用對象為 Adobe Analytics 系統管理員。本節重點放在新的連結追蹤參數，以及這些新參數如何在瀏覽器和裝置之間確保連結獨特性和一致性，並改善頁面上的連結重新定位處理。

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](../../../analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#section_634197EACD404AC086DF9A03B813C8C3). 如需進一步瞭解 Activity Map 收集 PII 資料的可能方式，請前往[這裡](../../../analyze/activity-map/lnk-tracking-overview.md#section_A9F016E64F33446F8916855D8C69A7C6)。

Activity Map 的連結追蹤是根據下列兩個 ID:

* 主要 ID: 這是連結的可識別參數。
* 連結地區: 這是次要參數，可讓使用者指定該頁面或地區中整體連結區域的代表字串。如果使用者未提供此參數，此參數可以自動產生。

## 主要 ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

如果 HTML 有 s_objectid，則主要 ID 預設為 s_objectid。否則會使用下列參數做為主要 ID (按照下列優先順序):

* Innertext
* Alttext
* Title
* Src
* Action

## 使用 InnerText 和使用連結動作 (URL) 的比較 {#section_70C3573E22274522A8CC035BF18EC468}

「連結動作」是當連結被點按時，網頁所採取的動作 - 通常是連結點按後造訪的 URL。使用連結動作時可能會遇到的問題包括:

* 兩個以上不同的連結具有相同 ID
* 連結的可讀性
* 單一連結具有多重動作 (取決於您用於檢視連結的裝置)

因此，我們改用 InnerText，比起連結動作 (URL) 具有以下優點:

* 可以良好表示連結身份。可以大幅降低主要 ID 重複項目，因為不常發生多個連結具有相同文字。
* 可確保主要 ID 在所有裝置和瀏覽器類型間保持一致性。
* 不受頁面上連結重新定位的影響。
* 改善可讀性，讓使用者可以在 Activity Map 外部分析連結追蹤報表。

## Link region {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

這個新屬性可讓使用者指定字串，用來代表連結所在的頁面地區。

例如，針對位在網頁之功能表區段的「聯絡我們」連結，使用者可能會想傳遞「功能表」(Menu) 地區參數。同樣地，對於位在網頁頁尾的「聯絡我們」連結，地區參數可以設為「頁尾」(footer)。

連結地區值並非設在連結本身，而是設在包含該地區的 DOM HTML 樹狀結構上的一個 HTML 元素中。使用「連結地區」具備下列優點:

* 可協助區分具相同主要 ID 的連結。
* 地區趨勢分析較不受網頁的動態方面影響。
* 使用者可查看某地區內績效最佳的連結。使用地區做為錨記，可以顯示頁面中目前隱藏之連結的覆蓋圖 (Ajax、鎖定)。
* 由於特定地區可在許多網頁間使用，因此地區可以取代頁面。可協助回答類似下列的問題: 我的「產品供應」地區在女性登陸頁面和男性登陸頁面哪個表現最佳?
* 地區本身是相關維度，可分析高度動態網頁。這是因為它可移除不斷變動連結所造成的雜訊: 例如，CNN 登陸頁面中的「最新消息」地區可能會有很多變動連結。但地區永遠存在。所以在地區層級針對許多天進行分析，應該可獲得有趣的結果。

**自訂地區追蹤**

您可以自訂連結的地區參數 (預設為連結 ID): 設為 "ID" 的標記會使用具有 "id" 參數的所有 HTML 元素做為「地區」。因此，將地區標記設為 "id" 最有可能傳回許多不同的地區 (數量即頁面上設定的 "ID" 數)。此外，如果您想要自訂性更強的實作，可將地區標記設定為更具體的項目，例如 "region_id"。

以下顯示一些使用預設地區 ID 屬性 "id" 的 HTML 範例。

```
<div id="content"> 
  <div id="breaking_news"> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
```

您也可使用任意字串識別碼 (以下範例中為 "lpos") 來標記元素，接著使用名稱 "lpos" 新增屬性。

```
s.ActivityMap.regionIDAttribute="lpos"; 
   
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

## Configuration variables {#section_634197EACD404AC086DF9A03B813C8C3}

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
   <td colname="col1"> s. ActivityMap. regionIDAttribute </td> 
   <td colname="col2"> 預設為 "id" 參數。您可將此變數設定為其他參數。 </td> 
   <td colname="col3"> 字串，用來識別 s.linkObject 的某些上階 (parent、parent.parent 等) 元素 (亦即<b>被點按的元素</b>) 中，做為地區 ID 的標記屬性。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. ActivityMap. link </td> 
   <td colname="col2"> 
    <code>//只能使用A標籤函數(cliceDelement){var linkID中的「title」屬性；if(cliceDelement&amp;&amp; CliceDelement. tagName. toupPercase()=='A'){linkID= clickelDelement. getAttribute. getAttribute('title')；} return linkId；} </code>
  </td> 
   <td colname="col3"> 函數，接受被點按的 HTMLElement，且應傳回代表<b>被點按的連結</b>的字串值。 <p>如果傳回值為 false (null、未定義、空字串、0)，將不會追蹤任何連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. ActivityMap. region </td> 
   <td colname="col2"> 
    <code>//只能使用與第一個ClassName相同的小寫版本，做為地區函數(cliceDelement){var regionId、ClassName；while(clickedDelement&amp;&amp;(cliceDelement= cliceDelement. parentNode)){regionId= clickedDelement. tagName；if(regionId){return regionId. toLowerCase()；}}} </code>
  </td> 
   <td colname="col3"> 函數，接受被點按的 HTMLElement，且應傳回代表<b>在點按時連結所在地區</b>的字串值。 <p>如果傳回值為 false (null、未定義、空字串、0)，將不會追蹤任何連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>//排除具有特殊linkExcludated CSS類別&lt;樣式&gt;. linkExcluded{display的連結：區塊；高度：px；左側：-9999px；溢位：隱藏；位置：絕對；width：px；}&lt;/style&gt;&lt; a href=「loc」&gt;連結會受到追蹤，因為連結沒有比對篩選器的隱藏文字。&lt;/a&gt;&lt; a href=「next-page.html」&gt;「連結」未追蹤，因為s. ActivityMap. linkExclusions已設定，且此連結具有比對篩選的隱藏文字。&lt; span class=「linkExcluded」&gt; exclude-link1&lt;/san&gt;&lt;/a&gt;&lt;/a&gt;&lt; a href=「next-page.html」&gt;「連結」未追蹤，因為s. ActivityMap. linkExclusions已設定，且此連結具有隱藏文字比對篩選。 &lt;span class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>接受以逗號分隔的字串清單以在連結文字中進行尋找的字串若找到，則該連結排除由 Activity Map 追蹤。若未設定，則 Activity Map 並未試圖停止追蹤該連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>//由ActivityMap&lt; div id=「links-includated」&gt;&lt; a href=「next-page.html」&gt;&gt;&gt;&gt;&gt;「連結」追蹤的頁面上的「排除」區域會受到追蹤，但不符合篩選器。&lt;/a&gt;&lt;/div&gt;&lt; div id=「links-excluded」&gt;&lt; a href=「next-page.html」&gt;&gt;&gt;&gt;「連結」，因為s. ActivityMap. regionExclusions已設定，且符合篩選條件。&lt;/a&gt; &lt;/div&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.regionExclusions = 'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>接受以逗號分隔的字串清單以在地區文字中進行尋找的字串。若找到，則該連結排除由 Activity Map 追蹤。若未設定，則 Activity Map 並未試圖停止追蹤該連結。 </p> </td> 
  </tr> 
 </tbody> 
</table>

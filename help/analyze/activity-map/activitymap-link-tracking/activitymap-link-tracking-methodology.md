---
description: 本節適用對象為 Adobe Analytics 系統管理員。本節重點放在新的連結追蹤參數，以及這些新參數如何在瀏覽器和裝置之間確保連結獨特性和一致性，並改善頁面上的連結重新定位處理。
title: 連結追蹤方法
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: a6b38c6e7a34c876524ebe15514ac205898549d0
workflow-type: ht
source-wordcount: '992'
ht-degree: 100%

---

# 連結追蹤方法

本節適用對象為 Adobe Analytics 系統管理員。本節重點放在新的連結追蹤參數，以及這些新參數如何在瀏覽器和裝置之間確保連結獨特性和一致性，並改善頁面上的連結重新定位處理。

>[!IMPORTANT]
>
>任何可能含有 PII (個人識別資訊) 之文字的連結，都應使用 [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=zh-Hant) 明確實作，或是使用 [s.ActivityMap.linkExclusions 或 s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars) 排除 ActivityMap 連結集合。如需進一步瞭解 Activity Map 收集 PII 資料的可能方式，請前往[這裡](/help/analyze/activity-map/lnk-tracking-overview.md)。

Activity Map 的連結追蹤是根據下列兩個 ID：

* 主要 ID：這是連結的可識別參數。
* 連結區域：這是次要參數，可讓使用者指定該頁面或區域中整體連結區域的代表字串。如果使用者未提供此參數，此參數可以自動產生。

## 主要 ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

如果 HTML 有 s_objectid，則主要 ID 預設為 s_objectid。否則會使用下列參數做為主要 ID (按照下列優先順序)：

* Innertext
* Alttext
* 標題
* Src
* 動作

## 使用 InnerText 和使用連結動作 (URL) 的比較 {#section_70C3573E22274522A8CC035BF18EC468}

「連結動作」是當連結被點按時，網頁所採取的動作 - 通常是連結點按後造訪的 URL。使用連結動作時可能會遇到的問題包括：

* 兩個以上不同的連結具有相同 ID
* 連結的可讀性
* 單一連結具有多重動作 (取決於您用於檢視連結的裝置)

因此，我們改用 InnerText，比起連結動作 (URL) 具有以下優點：

* 可以良好表示連結身份。可以大幅降低主要 ID 重複項目，因為不常發生多個連結具有相同文字。
* 可確保主要 ID 在所有裝置和瀏覽器類型間保持一致性。
* 不受頁面上連結重新定位的影響。
* 改善可讀性，讓使用者可以在 Activity Map 外部分析連結追蹤報表。

## 連結區域 {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

這個新屬性可讓使用者指定字串，用來代表連結所在的頁面區域。

例如，針對位在網頁之功能表區段的「聯絡我們」連結，使用者可能會想傳遞「功能表」(Menu) 區域參數。同樣地，對於位在網頁頁尾的「聯絡我們」連結，區域參數可以設為「頁尾」(footer)。

連結區域值並非設在連結本身，而是設在包含該區域的 DOM HTML 樹狀結構上的一個 HTML 元素中。使用「連結區域」具備下列優點：

* 可協助區分具相同主要 ID 的連結。
* 區域趨勢分析較不受網頁的動態方面影響。
* 使用者可查看某區域內績效最佳的連結。使用區域做為錨點，可以顯示頁面中目前隱藏之連結的覆蓋圖 (Ajax、鎖定)。
* 由於特定區域可在許多網頁間使用，因此區域可以取代頁面。這可協助回答類似下列問題：「我的『產品供應』區域在女性登陸頁面還是男性登陸頁面表現最佳？
* 區域本身是相關維度，可分析高度動態網頁。這是因為它可移除不斷變動連結所造成的雜訊：例如，CNN 登陸頁面中的「最新消息」區域可能會有很多變動連結。但區域永遠存在。所以在區域層級針對許多天進行分析，應該可獲得有趣的結果。

**自訂區域追蹤**

您可以自訂連結的區域參數 (預設為連結 ID)：設為 &quot;ID&quot; 的標記會使用具有 &quot;id&quot; 參數的所有 HTML 元素做為「區域」。因此，將區域標記設為 &quot;id&quot; 最有可能傳回許多不同的區域 (數量即頁面上設定的 &quot;ID&quot; 數)。此外，如果您想要自訂性更強的實作，可將區域標記設定為更具體的項目，例如 &quot;region_id&quot;。

以下顯示一些使用預設區域 ID 屬性 &quot;id&quot; 的 HTML 範例。

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

您也可使用任意字串識別碼 (以下範例中為「lpos」) 來標記元素，接著使用名稱「lpos」新增屬性。

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## 設定變數 {#configuration-vars}

請注意，以下所列變數僅供參考。Activity Map 在出廠時即已正確設定，但您可使用這些變數來自訂實作。

### `s.ActivityMap.regionIDAttribute`

字串：用來識別 `s.linkObject` 的某些上階 (parent、parent.parent 等) 元素 (亦即，**被點按的元素**) 中作為區域 ID 的標記屬性。

**範例**

預設為 &quot;id&quot; 參數。您可將此變數設定為其他參數。

### `s.ActivityMap.link`

函數：接受被點按的 `HTMLElement`，且應傳回代表被點按的連結的字串值。如果傳回值為 false (null、未定義、空字串、0)，將不會追蹤任何連結。

**範例**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

函數：接受被點按的 HTMLElement，且應傳回代表被點按時發現連結的&#x200B;**區域的字串值。**&#x200B;如果傳回值為 false (null、未定義、空字串、0)，將不會追蹤任何連結。

**範例**

```
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

### `s.ActivityMap.linkExclusions`

接受以逗號分隔的字串清單以在連結文字中進行尋找的字串若找到，則該連結排除由 Activity Map 追蹤。若未設定，則 Activity Map 並未試圖停止追蹤該連結。

**範例**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

接受以逗號分隔的字串清單以在區域文字中進行尋找的字串。若找到，則該連結排除由 Activity Map 追蹤。若未設定，則 Activity Map 並未試圖停止追蹤該連結。

**範例**

```
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```

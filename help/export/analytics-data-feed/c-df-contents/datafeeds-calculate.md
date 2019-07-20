---
description: 說明如何使用資料摘要來計算通用量度。
keywords: 資料饋送；工作；度量；前置欄；後置欄；機器人；日期篩選；事件字串；常見；公式
seo-description: 說明如何使用資料摘要來計算通用量度。
seo-title: 計算量度
solution: Analytics
title: 計算量度
topic: Reports & Analytics
uuid: a45ea5bb-7c83-468f-b94 a-63add78931 d7
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 計算量度

說明如何使用資料摘要來計算通用量度。

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## 機器人 {#section_06753B95800F47668AAF52E7227F27C8}

根據您報表套裝所定義的[機器人規則](https://marketing.adobe.com/resources/help/en_US/reference/?f=bot_rules)，會從資料饋送中排除機器人。

## 日期篩選 {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

透過篩選 `date_time` 欄位，包含您想納入之日期範圍的行。`date_time` 欄位是人類可讀性的(例如， `YYYY-MM-DD HH:MM:SS`)，並調整為報表套裝的時區。For example, `date_time starts with "2013-12"` includes hits from December 2013.

## 事件字串 {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. 建議您對 `post_event_list` 進行所有處理，因為它會消除重複記錄並已套用邏輯以移除具有相同 ID 的重複事件 (請參閱[事件序列化](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_event_serialization))。

如需事件 ID 與名稱對應，請參閱資料饋送所傳送的事件查閱。

如需事件的詳細資訊，請參閱[事件](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_events)。

## 通用量度的公式 {#section_E26A01C234484857BF8C74443222AE41}

下表包含計算數個通用量度的指示。

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 計算方式 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 頁面檢視 </td> 
   <td colname="col2"> <p> 頁面檢視可藉由計算 <code>post_pagename</code> 或 <code>post page_url</code> 中的值來得出。 </p> 
    <p>您可使用類似的邏輯來計算自訂連結: </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code>post_page_event = 100</code> 可計算自訂連結。 </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code>post_page_event = 101</code> 可計算下載連結。 </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code>post_page_event = 102</code> 可計算退出連結。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 造訪次數 </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">排除具有 <code>hit_source = 5,7,8,9</code> 的所有行。5、8 和 9 是使用資料來源上傳的摘要行。7 代表不應納入瀏覽次數和訪客計數的交易 ID 資料來源上傳。請參閱 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 點擊來源查閱 </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">結合 <code>post_visid_high</code>、<code>post_visid_low</code>、<code>visit_num</code> 和 <code>visit_start_time_gmt</code>*。計算結合的唯一數目。 </li> 
    </ol> <p>*在罕見的情況下，網際網路違規、系統不正確或使用自訂訪客 ID 可能會導致不屬於同一次<code>造訪</code>的相同訪客 ID 的 <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=metrics_visit" format="http" scope="external">visit_num</a> 值重複。若要避免發生問題，在計算造訪時請一併包含 <code>visit_start_time_gmt</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客 </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">排除具有 <code>hit_source = 5,7,8,9</code> 的所有行。5、8 和 9 是使用資料來源上傳的摘要行。7 代表不應納入瀏覽次數和訪客計數的交易 ID 資料來源上傳。請參閱 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 點擊來源查閱 </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">結合 <code>post_visid_high</code> 和 <code>post_visid_low</code>。計算結合的唯一數目。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件例項 </td> 
   <td colname="col2"> <p>在點擊上設定事件時，<code>post_event_list</code> 包含事件。<code>post_event_list</code> 已消除重複記錄，建議用於決定事件例項。 </p> <p>例如: </p> 
    <code>post_ event_ list=1,200 </code>
  <p>指出 <code>purchase</code> 和 <code>event1</code> 的例項。 </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">排除具有 <code>hit_source = 5,8,9</code> 的所有行。這些是使用資料來源上傳的摘要行。請參閱 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 點擊來源查閱 </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">計算 <code>post_event_list</code> 中出現的事件查閱值次數。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar 例項 </td> 
   <td colname="col2"> <p>在點擊上設定 eVar 時，<code>event_list</code> 包含 eVar 例項。 </p> <p>例如: </p> 
    <code>post_ event_ list&amp; amp；nbsp；=&amp; amp；nbsp；100,101,106 </code>
  <p>指出 <code>eVar1</code>、<code>eVar2</code> 和 <code>eVar7</code> 的例項。這表示在點擊上設定了這三個 eVar 的值。 </p> <p>若要計算 eVar 的例項，請使用上述<i>事件例項</i>中說明的相同邏輯，但改為計算 <code>post_event_list</code> 中出現的 eVar 查閱次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 逗留時間 </td> 
   <td colname="col2"> <p>若要計算逗留的時間，必須依瀏覽將點擊分群組，然後根據瀏覽中的點擊數排序。 </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">串接 <code>visid_high</code>、<code>visid_low</code> 及 <code>visit_num</code>，將瀏覽的點擊分群組。 </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">依 <code>visit_page_num</code> 將各個瀏覽的點擊排序。 </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">找到您設定用於追蹤逗留時間之值的點擊。例如:<code>點擊1：post_ prop1= red hit2：post_ prop1= blue </code>
  </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">將 hit 2 的 <code>post cust_hit_time</code> 減去 hit 1 的 <code>post_cust_hit_time</code>，可得知兩次點擊間的秒數。結果即是 <code>post_prop1=red</code> 的逗留時間。如果結果為負數，表示點擊不是按預期的順序發生，應捨棄計算結果。 </li> 
    </ol> <p>這個邏輯可以擴大去計算其他值的逗留時間。計算逗留時間時，Analytics 會根據 <code>track</code> (<code>page_event=0</code>) 或 <code>trackLink</code> (<code>page_event=10|11|12</code>) 呼叫設定值的時間，到下次頁面檢視 (<code>track</code> 呼叫) 的時間，來計算逗留時間。 </p> <p>當報告特定期間的逗留時間時，Marketing Reports &amp; Analytics 以及 Ad Hoc Analysis 會評估報告期間外的點擊，以判斷報告期間內值的逗留時間，唯期間的開始及/或結束日期落在月邊界時除外。由於這些計算很複雜，有可能難以與逗留時間量度完全對應。Data Warehouse 不會評估報告期間外的點擊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收入、訂購、單位 </td> 
   <td colname="col2"> <p>根據報表套裝的設定會套用貨幣轉換至 <code>post_product_list</code>，所以建議使用該欄。 </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">排除 <code>exclude_hit &gt; 0</code> 的所有行。 </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">排除具有 <code>hit_source = 5,8,9</code> 的所有行。5-9 代表使用資料來源上傳的摘要行。請參閱 <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> 點擊來源查閱 </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">忽略 <code>duplicate_purchase = 1</code> 之所有行的購買資料。此旗標指出購買為重複 (表示已經記錄過同一 <code>purchaseID</code> 的點擊)。 </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p><code>post_product_list</code> 使用 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_products" format="http" scope="external">s.products</a> 的相同語法，所以可以解析此字串以計算量度。例如: </p> 
      <code>；跨培訓人員；1；69.95；運動Socks；10；29.99 </code>
  <p>解析此字串後，您可以判定購買一雙運動鞋 (Cross Trainers) 收入 $69.95，這筆購買的總收入為 $99.94。 </p> </li> 
    </ol> <p>注意: Analytics 允許透過事件字串傳遞包含產品收入的貨幣事件，所以您可能也須計算不在產品字串中的收入。請參閱 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_events" format="http" scope="external">s.events</a> 中的<i>數值/貨幣事件</i>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

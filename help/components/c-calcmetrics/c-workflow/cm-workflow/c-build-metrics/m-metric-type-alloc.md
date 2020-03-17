---
description: 選取量度旁的齒輪圖示，即可指定量度類型和歸因模型。
title: 量度類型和歸因
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 量度類型和歸因

選取量度旁的齒輪圖示，即可指定量度類型和歸因模型。

* [量度類型](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [欄歸因模型](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [「線性配置」自 2018 年 7 月 19 日起的新運作方式](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## 量度類型 {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| 量度類型 | 定義 |
|---|---|
| 標準 | 這些量度就是在標準 [!DNL Analytics] 報表中使用的量度。如果某個公式由單一標準量度組成，則其顯示的資料將與其非計算量度相對應公式一樣。標準量度適合用來建立每個行項目專屬的計算量度。例如，[訂單] / [造訪] 會採用該特定條列項目的訂單，然後除以該特定條列項目的造訪次數。 |
| 總計 | 總計適用於每個行項目的報告期間。如果公式由單一總計量度組成，則會在每個行項目顯示相同的總數。總計量度適合用來建立要與網站資料總計比較的計算量度。例如，[訂單] / [造訪總次數] 可顯示相較於網站「全部」造訪次數的訂單比例，而不只是特定條列項目的造訪次數。 |

## 欄歸因模型 {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>[!DNL Analytics] 於 2018 年 7 月推出了[歸因 IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html)，修訂計算量度中配置模型的評估方式。這次變更中，使用非預設配置模型的計算量度已改為新的改良版歸因模型：
>
>* 如需非預設歸因模型的完整清單及支援的回溯時段，請參閱[歸因 IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) 文件。
>* 「行銷管道上次接觸」和「行銷管道首次接觸」配置模型將分別移轉至新的「上次接觸」和「首次接觸」屬性模型 (注意：「行銷管道」將不會遭到廢止，而是只會廢止出現在計算量度中的兩個配置模型)。
>* 此外，我們將修正「線性配置」的計算方式。如果客戶使用的是包含「線性」配置模型的計算量度，報表會稍微變更以反映修正後新的屬性模型。Analysis Workspace、[!UICONTROL Reports &amp; Analytics]、Reporting API、Report Builder 和 Ad Hoc Analysis 會反映此次計算量度變更。如需更多資訊，請參閱[「線性配置」自 2018 年 7 月 19 日起的新運作方式](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)。
>



## 「線性配置」自 2018 年 7 月 19 日起的新運作方式{#section_EDBB2E14A6C248C5A79C0913C02D7CA1}

2018 年 7 月，Adobe 已變更線性配置在計算量度中的呈報方式。此變更會影響 Analysis Workspace、Ad Hoc Analysis、[!UICONTROL Reports &amp; Analytics]、Report Builder、Activity Map 和 Reporting API。此次變更主要影響 eVar 和其他具持續性的維度。請注意，這些變更只會套用至計算量度，不會影響其他使用線性配置的報表 (例如 [!UICONTROL Reports &amp; Analytics] 的「頁面」報表)。其他使用線性配置的報表將繼續使用目前的線性配置方法。

下列範例將說明具有線性配置的計算量度在報表中將如何變更：

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> 點擊 1 </th> 
   <th colname="col3" class="entry"> 點擊 2 </th> 
   <th colname="col4" class="entry"> 點擊 3 </th> 
   <th colname="col5" class="entry"> 點擊 4 </th> 
   <th colname="col6" class="entry"> 點擊 5 </th> 
   <th colname="col7" class="entry"> 點擊 6 </th> 
   <th colname="col8" class="entry"> 點擊 7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>傳入資料 </p> </td> 
   <td colname="col2"> 促銷活動 A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促銷活動 A </td> 
   <td colname="col5"> 促銷活動 B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> 促銷活動 C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次接觸 eVar </p> </td> 
   <td colname="col2"> 促銷活動 A </td> 
   <td colname="col3"> 促銷活動 A </td> 
   <td colname="col4"> 促銷活動 A </td> 
   <td colname="col5"> 促銷活動 B </td> 
   <td colname="col6"> 促銷活動 B </td> 
   <td colname="col7"> 促銷活動 C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>首次接觸 eVar </p> </td> 
   <td colname="col2"> 促銷活動 A </td> 
   <td colname="col3"> 促銷活動 A </td> 
   <td colname="col4"> 促銷活動 A </td> 
   <td colname="col5"> 促銷活動 A </td> 
   <td colname="col6"> 促銷活動 A </td> 
   <td colname="col7"> 促銷活動 A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>範例 prop </p> </td> 
   <td colname="col2"> 促銷活動 A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促銷活動 A </td> 
   <td colname="col5"> 促銷活動 B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> 促銷活動 C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

在本範例中，A、B和 C 值在點擊 1、3、4 和 6 時傳入，然後在點擊 7 時進行 $10 的購物。在第二列中，這些值會持續存在於上次接觸瀏覽的所有點擊間。第三列說明首次接觸瀏覽持續性最後，最後一列說明如何針對不具持續性的 PROP 記錄資料。

**2018 年 7 月前的線性配置運作方式摘要**

2018 年 7 月 19 日前，線性歸因是在首次接觸或上次接觸持續性發生後才開始計算。也就是說，就上述的上次接觸 eVar 而言，$10 將分配如下：A = 10 * (3/6) = $5，B = 10 * (2/6) = $3.33，C = 10 * (1/6) = $1.67。

就上述的首次接觸 eVar 而言，$10 會全數分配給 A。對 prop 而言：A = 10 * (2/4) = $5，B = 10 * (1/4) = $2.50，而 C = 10 * (1/4) = $2.50。目前線性配置的運作方式總結如下：

| 值 | 目前的上次接觸 eVar | 目前的首次接觸 eVar | 目前的 Prop |
|---|---|---|---|
| 促銷活動 A | $5.00 | $10.00 | $5.00 |
| 促銷活動 B | $3.33 | $0 | $2.50 |
| 促銷活動 C | $1.67 | $0 | $2.50 |
| 總計 | $10.00 | $10.00 | $10.00 |

**自 2018 年 7 月 19 日起的線性配置運作方式摘要**

自 7 月 19 日起，我們在計算量度中修正了這種行為。[!DNL Analytics] 不再使用以上次接觸或首次接觸為基礎的持續值，現在只會使用傳入的值 (上表的第一列)。同樣地，維度配置設定不再影響線性配置的計算方式 (亦即會以同樣的方式處理 prop 和 eVar)，且結果會反映原本傳入的內容，而非可能持續存在的首次或上次接觸值。因此，在三個案例中，A = 10 * (2/4) = $5，B = 10 * (1/4) = $2.50，C = 10 * (1/4) = $2.50。

| 值 | 新的上次接觸 eVar | 新的首次接觸 eVar | 新的 Prop |
|---|---|---|---|
| 促銷活動 A | $5.00 | $5.00 | $5.00 |
| 促銷活動 B | $2.50 | $2.50 | $2.50 |
| 促銷活動 C | $2.50 | $2.50 | $2.50 |
| 總計 | $10.00 | $10.00 | $10.00 |

<!-- 

<p>Additionally, as part of this change, [!DNL Analytics] is <b>changing how multiple sequential successes</b> are treated. In the following example, 7 hits occurred in the same visit with two orders, one $10 order on hit 4, and one $5 order on hit 7: </p> 
<table id="table_4647AA466D1447F6961DDC10468FCCE1"> 
 <tgroup cols="8">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="1.04*" />
  <colspec colnum="3" colname="col3" colwidth="1.02*" />
  <colspec colnum="4" colname="col4" colwidth="1.02*" />
  <colspec colnum="5" colname="col5" colwidth="1.03*" />
  <colspec colnum="6" colname="col6" colwidth="1.02*" />
  <colspec colnum="7" colname="col7" colwidth="1.02*" />
  <colspec colnum="8" colname="col8" colwidth="1.03*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry"> Hit 1 </th> 
    <th colname="col3" class="entry"> Hit 2 </th> 
    <th colname="col4" class="entry"> Hit 3 </th> 
    <th colname="col5" class="entry"> Hit 4 </th> 
    <th colname="col6" class="entry"> Hit 5 </th> 
    <th colname="col7" class="entry"> Hit 6 </th> 
    <th colname="col8" class="entry"> Hit 7 </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Data Sent In </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Last Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO B </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO B </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>First Touch eVar </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> PROMO A </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> PROMO A </td> 
    <td colname="col7"> PROMO A </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Example prop </p> </td> 
    <td colname="col2"> PROMO A </td> 
    <td colname="col3"> - </td> 
    <td colname="col4"> PROMO A </td> 
    <td colname="col5"> $10 </td> 
    <td colname="col6"> - </td> 
    <td colname="col7"> PROMO C </td> 
    <td colname="col8"> $5 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p>Currently (<b>prior to July 19, 2018</b>), linear attribution would carry forward past the initial conversion and persist into the second conversion </p> 
<ul id="ul_FD09813B59F04FF2A96A70BBE0A8F349"> 
 <li id="li_2EC965DDAE334C1795530F7C6F1674C5">In our first-touch eVar example, the total revenue for each promotion would be calculated using the promos prior to conversion on hit 4 for revenue on hit 4, but all promos for the conversion on hit 7. </li> 
 <li id="li_687C03C4B0A941AA800084F324A95FD6">In our last-touch eVar example, this would be: A = (2/3) * 10 + (2/5) * 5 = $8.66, B = (1/3) * 10 + (2/5) * 5 = $5.33, C = (1/5) * 5 = $1.00. In our FT eVar example: A = (3/3) * 10 + (5/5) * 5 = $15.00, and for the prop: A = (1/2) * 10 + (1/3) * 5 = $6.66, B = (1/2) * 10 + (1/3) * 5 = $6.66, and C = (1/3) * 5 = $1.66. </li> 
</ul> 
<p>Resulting in a distribution as follows: </p> 
<table id="table_6A066E602BF641B0BD4B175EE9753C6E"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> Current Last Touch eVar </th> 
    <th colname="col3" class="entry"> Current First Touch eVar </th> 
    <th colname="col4" class="entry"> Current Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $8.66 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.33 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $6.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $1.00 </td> 
    <td colname="col3"> $0.00 </td> 
    <td colname="col4"> $1.66 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table> 
<p> </p> 
<p><b>After July 19, 2018</b>, [!DNL Analytics] will treat each sequence of conversions independently, meaning linear attribution will no longer carry forward from one conversion to another. In the previous example, attribution will always be treated the same way (regardless of the eVar allocation settings as stated above) and will be calculated as follows: A = (1/2) * 10 = $5, B = (1/2) * 10 = $5, and C = (1/1) * 5 = $5. To summarize: </p> 
<table id="table_2D39CCD158BF488EA404324DF50B9579"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <colspec colnum="4" colname="col4" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Values </th> 
    <th colname="col2" class="entry"> New Last Touch eVar </th> 
    <th colname="col3" class="entry"> New First Touch eVar </th> 
    <th colname="col4" class="entry"> New Prop </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> PROMO A </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO B </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PROMO C </td> 
    <td colname="col2"> $5.00 </td> 
    <td colname="col3"> $5.00 </td> 
    <td colname="col4"> $5.00 </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Total </td> 
    <td colname="col2"> $15.00 </td> 
    <td colname="col3"> $15.00 </td> 
    <td colname="col4"> $15.00 </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->


---
description: 選取量度旁的齒輪圖示可讓您指定量度類型和歸因模型。
title: 量度類型和歸因
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# 量度類型和歸因

選取量度旁的齒輪圖示可讓您指定量度類型和歸因模型。

* [量度類型](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_34A86FB402F94E988724232283BF18B7)
* [欄歸因模型](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_F9690FD1943B403AB28E2FAC54EFE032)
* [線性配置的運作方式（自2018年7月19日起）](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)

## 量度類型 {#section_34A86FB402F94E988724232283BF18B7}

![](assets/cm_type_alloc.png)

| 量度類型 | 定義 |
|---|---|
| 標準 | 這些量度就是在標準 [!DNL Analytics] 報表中使用的量度。如果公式由單一標準量度組成，則會顯示與非計算量度對應的相同資料。 標準量度對於建立每個個別行項目專屬的計算量度非常有用。 例如，[訂單] / [造訪] 會採用該特定條列項目的訂單，然後除以該特定條列項目的造訪次數。 |
| 總計 | 在每個行項目中使用報告期間的總計。 如果公式由單一總量度組成，則會在每個行項目上顯示相同的總數。 總量度對於建立與網站總資料比較的計算量度非常有用。 例如，[訂單] / [造訪總次數] 可顯示相較於網站「全部」造訪次數的訂單比例，而不只是特定條列項目的造訪次數。 |

## 欄歸因模型 {#section_F9690FD1943B403AB28E2FAC54EFE032}

>[!IMPORTANT]
>
>[!DNL Analytics] 於 2018 年 7 月推出了[歸因 IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html)，修訂計算量度中配置模型的評估方式。這次變更中，使用非預設配置模型的計算量度已改為新的改良版歸因模型：
>
>* 如需非預設歸因模型的完整清單以及支援的回顧視窗，請參閱 [Attribution IQ檔案](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html) 。
>* 「行銷管道上次接觸」和「行銷管道首次接觸」配置模型將分別移轉至新的「上次接觸」和「首次接觸」屬性模型 (注意：「行銷管道」將不會遭到廢止，而是只會廢止出現在計算量度中的兩個配置模型)。
>* 此外，我們將修正「線性配置」的計算方式。如果客戶使用的是包含「線性」配置模型的計算量度，報表會稍微變更以反映修正後新的屬性模型。Analysis Workspace、Reports &amp; Analytics、Reporting API、Report Builder 和 Ad Hoc Analysis 會反映此次計算量度變更。如需詳細資訊，請 **參閱下方的「線性配置」運作方式(自2018年7月19日起**)。
>



## 線性配置的運作方式（自2018年7月19日起）

2018 年 7 月，Adobe 已變更線性配置在計算量度中的呈報方式。此變更會影響 Analysis Workspace、Ad Hoc Analysis、Reports &amp; Analytics、Report Builder、Activity Map 和 Reporting API。此次變更主要影響 eVar 和其他具持續性的維度。請注意，這些變更只會套用至計算量度，不會影響其他使用線性配置的報表 (例如 Reports &amp; Analytics 的「頁面」報表)。使用線性配置的其他報表將繼續使用現有的線性配置方法。

下列範例將說明具有線性配置的計算量度在報表中將如何變更：

<table id="table_E66D066A3E7B4232BBC220775F8B985A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> 點擊1 </th> 
   <th colname="col3" class="entry"> 點擊2 </th> 
   <th colname="col4" class="entry"> 點擊3 </th> 
   <th colname="col5" class="entry"> 點擊4 </th> 
   <th colname="col6" class="entry"> 點擊5 </th> 
   <th colname="col7" class="entry"> 點擊6 </th> 
   <th colname="col8" class="entry"> 點擊7 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>傳送資料 </p> </td> 
   <td colname="col2"> 促銷活動A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促銷活動A </td> 
   <td colname="col5"> 促銷B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> 促銷C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次接觸eVar </p> </td> 
   <td colname="col2"> 促銷活動A </td> 
   <td colname="col3"> 促銷活動A </td> 
   <td colname="col4"> 促銷活動A </td> 
   <td colname="col5"> 促銷B </td> 
   <td colname="col6"> 促銷B </td> 
   <td colname="col7"> 促銷C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>首次接觸eVar </p> </td> 
   <td colname="col2"> 促銷活動A </td> 
   <td colname="col3"> 促銷活動A </td> 
   <td colname="col4"> 促銷活動A </td> 
   <td colname="col5"> 促銷活動A </td> 
   <td colname="col6"> 促銷活動A </td> 
   <td colname="col7"> 促銷活動A </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>範例prop </p> </td> 
   <td colname="col2"> 促銷活動A </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 促銷活動A </td> 
   <td colname="col5"> 促銷B </td> 
   <td colname="col6"> - </td> 
   <td colname="col7"> 促銷C </td> 
   <td colname="col8"> $10 </td> 
  </tr> 
 </tbody> 
</table>

在此範例中，值A、B和C已傳送至點擊1、3、4和6的變數，然後才在點擊7進行$10購買。 在第二列中，這些值會以上次接觸瀏覽為基礎持續存在於點擊之間。 第三列說明首次接觸瀏覽的永續性。 最後，最後一列說明如何記錄沒有永續性之prop的資料。

## 2018年7月前線性分配如何運作

在2018年7月19日之前，線性歸因是在首次接觸或上次接觸持續發生後計算。 也就是說，就上述的上次接觸 eVar 而言，$10 將分配如下：A = 10 * (3/6) = $5，B = 10 * (2/6) = $3.33，C = 10 * (1/6) = $1.67。

就上述的首次接觸 eVar 而言，$10 會全數分配給 A。對 prop 而言：A = 10 * (2/4) = $5，B = 10 * (1/4) = $2.50，而 C = 10 * (1/4) = $2.50。目前線性配置的運作方式總結如下：

| 值 | 目前上次接觸eVar | 目前首次接觸eVar | 目前的Prop |
|---|---|---|---|
| 促銷活動A | $5.00 | $10.00 | $5.00 |
| 促銷B | $3.33 | $0 | $2.50 |
| 促銷C | $1.67 | $0 | $2.50 |
| 總計 | $10.00 | $10.00 | $10.00 |

**截至2018年7月19日線性分配如何運作的摘要**

在7月19日之後，我們修正了計算量度中的此行為。 [!DNL Analytics] 不再使用以上次接觸或首次接觸為基礎的持續值，現在只會使用傳入的值 (上表的第一列)。因此，維度配置設定不會再影響線性配置的計算方式（也就是說，prop和eVar會以相同的方式處理），而結果會反映原本傳入的內容，而非可能持續存在的首次或上次接觸值。 因此，在這三種情況中，A = 10 *(2/4)= $5,B = 10 *(1/4)= $2.50,C = 10 *(1/4)= $2.50。

| 值 | 新的上次接觸eVar | 新的首次接觸eVar | 新Prop |
|---|---|---|---|
| 促銷活動A | $5.00 | $5.00 | $5.00 |
| 促銷B | $2.50 | $2.50 | $2.50 |
| 促銷C | $2.50 | $2.50 | $2.50 |
| 總計 | $10.00 | $10.00 | $10.00 |


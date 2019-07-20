---
description: 計算與進階計算 (或衍生) 量度為您可從現有量度建立的自訂量度。
keywords: 計算量度；衍生度量；進階計算量度
seo-description: 計算與進階計算 (或衍生) 量度為您可從現有量度建立的自訂量度。
seo-title: 計算與進階計算 (衍生) 量度
title: 計算與進階計算 (衍生) 量度
uuid: 2553c115-b15 a-4109-1de2-733dbc1 eb9 e
translation-type: tm+mt
source-git-commit: fb27d500a725a540e632952295aa2ea3a3a21fb6

---


# 計算與進階計算 (衍生) 量度

計算與進階計算 (或衍生) 量度為您可從現有量度建立的自訂量度。

>[!IMPORTANT]
>
>In July 2018, Adobe introduced [Attribution IQ](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/attribution.html), which revised the way allocation models in calculated metrics are evaluated. 這次變更中，使用非預設配置模型的計算量度已改為新的改良版歸因模型:
>
>* 「行銷管道上次接觸」和「行銷管道首次接觸」配置模型分別移轉至新的「上次接觸」和「首次接觸」歸因模型(注意：「行銷管道」尚未過時-只有出現在計算量度中的兩個配置模型才有支援)。
>* 此外，我們也修正了線性配置的計算方式。如果客戶使用的是包含「線性」配置模型的計算量度，報表會稍微變更以反映修正後新的屬性模型。This change to calculated metrics is reflected in [!UICONTROL Analysis Workspace], [!UICONTROL Reports &amp; Analytics], the Reporting API, Report Builder, and Ad Hoc Analysis. 如需更多資訊，請參閱[「線性配置」自 2018 年 7 月 19 日起的新運作方式](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1)。


我們的計算量度工具可讓您以極為靈活的方式建立、管理和規劃量度。They allow you as marketers, product managers and analysts to ask questions of the data without having to change your [!DNL Analytics] implementation. The custom metrics available in each [!DNL Analytics] package are:

* Adobe [!DNL Analytics] Foundation: Calculated
* [Adobe Analytics Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html)：計算+進階計算
* [Adobe Analytics Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html): 計算 + 進階計算
* [Adobe Analytics Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html): 計算 + 進階計算

以下為計算量度與進階計算量度功能比較:

| Builder 選項 | 計算量度 | 進階計算 (衍生) 量度 |
|---|---|---|
| [格式類型 (小數、時間、百分比、貨幣)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#concept_5EC82A91EB9C44FC870326C85F9D0B18) | 是 | 是 |
| [歸因變更 (預設、線性、參與率等)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) | 是 | 是 |
| [量度類型 (標準、總計)](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#concept_B7A1FCFEFA9D4C4883208ACE8C9C8E5E) | 是 | 是 |
| 基本運算元 (加、減、乘、除) | 是 | 是 |
| [套用區段](../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md#concept_21C77BD86E7E45E79AF030D8ED54DB3E) | 否 | 是 |
| [基本函數 (計數、abs 值、平均值等)](../../components/c-calcmetrics/cm-reference/cm-functions.md#concept_E3022D5EEEE145B69A23438BAF7016B2) | 否 | 是 |
| [進階函數 (迴歸、if/then、t 分數等)](../../components/c-calcmetrics/cm-reference/cm-adv-functions.md#concept_A5FB9127D70F4E1AA02D1ACBF4F54174) | 否 | 是 |

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* Create metrics across [!UICONTROL Analysis Workspace], [!UICONTROL Reports &amp; Analytics], [!UICONTROL Ad Hoc Analysis], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis].
* [無須變更實施](https://youtu.be/CuQTm9RaUpY)，即可建立衍生自報表執行時間的區段量度。因為這些量度的根據是區段，所以可查看其歷史資料。
* 在報表套裝間共用量度。這表示所有新建立的量度都會套用至相同登入公司的所有報表套裝。
* (僅限進階計算量度) 量度上的區段。例如，您可以建立「新訪客」的量度，計算這是他們第一次作業的人員數量。
* (僅限進階計算量度) 納入統計函數以協助您說明資料。例如，您可以計算報表中的項目數或加入每個項目的標準差數字。
* Utilize metrics created in [!UICONTROL Ad Hoc Analysis] in the other [!DNL Analytics] tools and vice versa.

   >[!NOTE]
   >
   >您可以繼續在臨機分析中建立量度。其計算量度產生器使用者介面現在類似於新的量度產生器。

## 限制 {#section_CB878B02451541D68A68B508D4DBD19A}

Some [!DNL Analytics] features let you use events but not calculated metrics:

* Reports &amp; Analytics 中的「漏斗」
* Analysis Workspace 中的「副產品」
* [!UICONTROL Analysis Workspace 中的「世代分析」]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 區段]
* [!UICONTROL 即時報表]
* [!UICONTROL 目前的資料報表]
* [!DNL Analytics] for [!DNL Target]

## 工具 {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Here is a short overview of the [!UICONTROL Calculated Metrics] tools:

<table id="table_520AFE97DB514958ABE23FD3C9CE0ABD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工具 </th> 
   <th colname="col2" class="entry"> 功能 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#concept_5EC82A91EB9C44FC870326C85F9D0B18" format="dita" scope="local"> 計算量度產生器</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E6F02AB9DF204C2F9A0AC92A31594B3E"> 
     <li id="li_A4A6E716374243A190C539A3F4A41C0C">使用進階配置模型建立計算量度和進階計算量度。 </li> 
     <li id="li_C8C97BA4E227463E98077ABA5818FFC6">新增區段內嵌至量度公式。 </li> 
     <li id="li_8503D9E06A3C46569B5CDB4B90F72446">比較同一份報表中的區段。例如，比較當地訪客和國際訪客。 </li> 
     <li id="li_4B528FDE1F96400DBA0D3276408FF919">使用統計函數。 </li> 
     <li id="li_C1162B1EA6784B8189A8A87E2B0DA79A">提供詳細的量度說明 (顯示其用途、使用位置、不應使用的位置)。 </li> 
     <li id="li_DEA13F5E8BF94AF1B311C467FE6E2A74">複製定義至新量度。 </li> 
     <li id="li_8C21F55015D44910904202D2BF74221C">提供內嵌量度預覽。 </li> 
     <li id="li_3704F66C321C477F9D4F52E068C231BD">設定量度極性，指定當特定自訂事件 (量度) 上升時是好事還是壞事。 </li> 
     <li id="li_9D45319FA965476FB1C90DE8AA72BBD7">標記量度。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md#concept_BA6815CB06D842D5825766396B691653" format="dita" scope="local"> 計算量度管理員</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E4D20D5DD3904CC6A85785B5BD4C1B1E"> 
     <li id="li_E0B216BA1478406EB6212263DF71D85B">與他人共用量度。 </li> 
     <li id="li_96EB16FAF3454211AAEF78EA5B08927F">核准和管理量度。 </li> 
     <li id="li_3ADBD2428EAC4B0AA61222D87C3AF2B7">組織 (標記) 量度，讓別人找得到。 </li> 
     <li id="li_726F3C3390744E49BA63606FE196880E">刪除量度。 </li> 
     <li id="li_F306BA4FA8AF4A6E987BA62634659A2F">重新命名量度。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度選擇器邊欄 </td> 
   <td colname="col2"> <p>Replaces the <span class="uicontrol"> Show Metrics</span> popup in [!UICONTROL Reports &amp; Analytics]. </p> <p>此邊欄可讓您搜尋並新增/套用量度至報表。您也可以變更<a href="../../components/c-calcmetrics/c-workflow/cm-workflow/cm-finding.md#concept_A09845053A934CB7B755391D76E76C08" format="dita" scope="local">排序</a>順序 (選項為: 字母順序、建議、經常使用、最近使用。)此外，您也可以篩選報表套裝，只顯示在特定報表套裝中建立的量度。 </p> <p>若要存取此量度選擇器，請按一下報表左側的「量度」圖示 <img placement="inline"  src="assets/metrics_icon.png" width="30px" id="image_2C6F20B4E634486B95BACD4CA47EF991" />。量度選擇器的外觀如下: </p> <p><img placement="break" align="center"  src="assets/metrics_rail.png" width="200px" id="image_379523E9AFEC4CF08D20C42C740AA358" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/README.md" format="https" scope="external"> 計算量度的 API</a> </td> 
   <td colname="col2"> <p>Adobe Analytics2.0API集的一部分。 </p> </td> 
  </tr> 
 </tbody> 
</table>


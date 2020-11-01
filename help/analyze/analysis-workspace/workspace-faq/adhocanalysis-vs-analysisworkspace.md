---
description: 比較 Analysis Workspace 與 Ad Hoc Analysis 的術語和工作
title: 比較 Analysis Workspace 與 Ad Hoc Analysis
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 80%

---


# 比較 Analysis Workspace 與 Ad Hoc Analysis

>[!IMPORTANT]
>
>Adobe將臨機分析移至2021年3月1日終止。 [更多詳情](https://adobe.ly/discoverworkspace)

比較 Analysis Workspace 與 Ad Hoc Analysis 的術語和工作

Analysis Workspace 將 Ad Hoc Analysis 的許多功能帶入瀏覽器工作流程。兩項產品的部分術語和功能相同，而 Analysis Workspace 中加入了一些新的分析用語和方法。

如需這兩項產品的重要功能技術比較和系統需求相關資訊，請前往[這裡](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-overview/analytics-product-comparison.html)。

## 重要術語的比較 {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| 專案 | 工作區或專案 |
| 工作區 | 面板 |
| 報表 | 自由表格 |
| 圖表／圖表 | 視覺效果 |
| 階層：專案 > 工作區> 報表 | 階層：專案 > 面板 > 表格 |
| 排名、趨勢、總計報表範本 | 自由表格視覺效果 |
| 流量範本 | 流量視覺效果 |
| 流失 | 流失視覺效果 |

## 重要工作的比較 {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysis任務 </th> 
   <th colname="col2" class="entry"> Analysis Workspace 工作 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>新增維度和區段至量度欄 </p> </td> 
   <td colname="col2"> <p>您可以將維度項目或區段帶入作為欄標頭，輕鬆地建立量度的比較視圖。<a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html"  > 影片：在分析工作區中新增維度和度量至專案</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>套用區段 </p> </td> 
   <td colname="col2"> <p>「區段」元件功能表下有「區段」，可以套用到 Analysis Workspace 中的 3 個地方： </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE"><b>面板層級</b>，會套用至面板中的許多視覺效果。這類似在 Ad Hoc 中將區段套用至工作區。 </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">作為<b>表格中的列</b>。這類似在 Ad Hoc 中將區段新增至表格產生器的「列/劃分」。 </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">作為<b>表格中的欄</b>。這類似在 Ad Hoc Analysis 中將區段新增至表格產生器的「列」，或在 Ad Hoc Analysis 中在報表層級套用區段。 </li> 
    </ol> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/applying-segments/applying-segments-to-your-analysis-workspace-project.html"  > 影片：在工作區中使用區段</a> </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/panel-level-segments.html"  > 影片：將區段套用至面板</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>建立暫時 (「臨機」) 區段 </p> </td> 
   <td colname="col2"> <p>您可以在 Analysis Workspace 中<a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >建立立即的暫時 (「臨機」) 區段</a>，做法是將維度項目拖放至面板頂端的區段拖放區域。此外，您可在面板拖放區域中新增下拉式篩選器，一次建立許多暫時區段，這會啟用控制的專案互動。 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/applying-segments/ad-hoc-temporary-segments.html"  > 影片：分析工作區中的臨機區段</a> </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/applying-segments/using-drop-down-filters.html"  > 影片：Analysis Workspace 中的下拉式篩選器</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>選擇日期範圍和精細度 </p> </td> 
   <td colname="col2"> <p>日期範圍和粒度在「時間」元件功能表下，有 3 種使用方式： </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">日期範圍可套用至欄/列，並覆蓋選取的面板日期範圍。這類似報表層級的日期範圍。 </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">「套用」會將日期範圍套用至面板中的所有視覺效果。這類似 Ad Hoc Analysis 中工作區的日期範圍。 </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">「套用至所有面板」會將日期範圍套用至工作區專案中的所有面板。這類似 Ad Hoc Analysis 中專案的日期範圍。 </li> 
    </ol> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html"  > 影片：使用 Analysis Workspace 中的日期</a> </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/creating-custom-date-ranges-in-analysis-workspace.html"  > 影片：自訂日期範圍</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用流失和轉換漏斗 </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  >流失視覺效果</a>在 Analysis Workspace 中的「視覺效果」元件功能表下。與 Ad Hoc Analysis 的相似之處： </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">流失可以跨越造訪或訪客，且可以選擇包含「所有造訪」。可以透過右鍵功能表快速分析流失趨勢。 </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">可使用 OR 運算子連接維度項目 (類似於群組)，且可在漏斗中使用事件。 </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">也可以透過右鍵功能表演算流過和流失的後續步驟。 </li> 
    </ol> <p>此外，Analysis Workspace 中的流失也允許在步驟中使用<a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  >混合維度</a>，這是 Ad Hoc Analysis 的一項改進。步驟中的混合維度是以 AND 運算子處理。 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/fallout-visualization.html"  > 影片：流失視覺化</a> </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/multi-dimensional-fallout.html"  > 影片：使用多個流失維度</a> </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/comparing-segments-in-fallout.html"  > 影片：比較流失中的區段</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檢查流量 (路徑) </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  >流量視覺效果</a>在 Analysis Workspace 中的「視覺效果」元件功能表下。與 Ad Hoc Analysis 的相似之處： </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">流量可跨越造訪或訪客。 </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">重要統計資料是以 % 路徑視圖顯示。 </li> 
    </ul> <p>此外，流量允許使用<a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  >混合維度</a>及以滑鼠右鍵按一下並建立區段，這是 Ad Hoc Analysis 的改進項目。 </p> <p>目前，Analysis Workspace 中的「流量」<b>無法</b>讓使用者選擇成功事件。 </li> 
    </ul> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization.html"  > 影片：流量視覺效果概述</a> </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow.html"  > 影片：多維度流量</a> </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/expanding-on-flow-visualization.html"  > 影片：從流量建立區段</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>執行無限劃分 </p> </td> 
   <td colname="col2"> <p>Analysis Workspace 可讓您在瀏覽器中鑽研無限層級。可以混合區段和維度。可以透過多項選取然後拖曳劃分維度同時劃分多個維度項目 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/dimension-breakdown-by-position.html"  > 影片：改進的劃分</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>快速顯示資料趨勢 </p> </td> 
   <td colname="col2"> <p>按一下報表列中的圖表圖示，可以快速將資料視覺化。此外，這些快速視覺效果會連結到來源表格，因此當您按表格中不同的值，圖表也會自動更新。 </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/dimension-graph-live-linking.html"  > 影片：維度圖表即時連結</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>選取報表套裝 </p> </td> 
   <td colname="col2"> <p>可在 Analysis Workspace 中將多個報表套裝新增至單一專案。  </p> <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace.html"  > 影片：工作區中的多個報表套裝</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>歸因 IQ </p> </td> 
   <td colname="col2"> <p>您可以使用 Analysis Workspace 中的<a href="/help/analyze/analysis-workspace/attribution/overview.md"  >歸因 IQ</a>，將許多新類型的歸因模型新增至自由表格、視覺效果和計算量度中。包含 10 種以上規則型和演算法模型。 </p>  <p><a href="https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables.html"  > 影片：自由表格的歸因 IQ</a> </p> </td> 
  </tr>  
 </tbody> 
</table>


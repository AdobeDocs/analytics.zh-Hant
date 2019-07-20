---
description: 'null'
seo-description: 'null'
seo-title: 歸因 IQ 常見問題集
title: 歸因 IQ 常見問題集
uuid: 90961172-869d-4ed3-aba5-52374e53 b603
translation-type: tm+mt
source-git-commit: ab2cda6d10bfeee13262581578bcdb4746112296

---


# 歸因 IQ 常見問題集

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>問: 為什麼當我使用新的歸因模型時，「無」行項目有時會獲得比我預期中更高的評分?</b> </p> </td> 
   <td colname="col2"> <p>答: 這很可能是因為您選取了<a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A" format="dita" scope="local">這裡</a>所述的報告視窗。這種情況最常見於您從當月第一天開始報告視窗，而您使用「訪客」(報告視窗) 回顧。若要擷取額外的歸因回顧 (並減少「無」行項目)，請嘗試在您的報告視窗納入較長的時間範圍。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 我在使用歸因模型時，有時會在報告中看到報告視窗以外的日期，為什麽？</b> </p> </td> 
   <td colname="col2"> <p>答: 這些額外的日期是訪客報告回溯視窗的結果，請參閱<a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md" format="dita" scope="local">這裡</a>的說明。<a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html" format="html" scope="external">資料顯示於報告視窗之外</a>一文將說明此現象發生的原因。Adobe Analytics 將在近期版本中篩選這些額外表格列。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 我是否可以透過歸因模型使用自訂回溯視窗？</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html" format="html" scope="external"> Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 我何時應該使用「造訪」歸因回溯或「訪客」歸因回溯？</b> </p> </td> 
   <td colname="col2"> <p>答: 歸因回溯的選擇取決於您的使用情形。如果您的轉換考量週期通常較長 (比單次造訪時間長)，建議您使用訪客回溯，或建立 VRS，讓造訪能更精確反映考量週期長度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 歸因模型是否可在資料摘要或 Data Warehouse 中使用？</b> </p> </td> 
   <td colname="col2"> <p>答: 否。因為我們將在報告期間使用<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">報告資料處理</a>來計算歸因模型，您無法讓歸因模型反映到資料摘要或 Data Warehouse。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 我是否只能在啟用「報表時間處理」的情況下使用「虛擬報表套裝」時才能使用歸因模型？</b> </p> </td> 
   <td colname="col2"> <p>答: 否，當歸因模型在後端使用<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">報表時間處理</a>時，我們就會在 VRS 和基本報告套裝提供歸因模型供您使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: Analysis Workspace 的歸因 IQ 是否支援資料驅動或演算法的歸因模型？</b> </p> </td> 
   <td colname="col2"> <p>答: Analysis Workspace 目前尚未支援，但我們正在積極預備這項功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 是否有歸因 IQ 不支援的維度或量度？</b> </p> </td> 
   <td colname="col2"> <p>答：所有維度均支援歸因IQ。</p> 
    <p><u>不</u>支援的量度 (因為基本上不可能) 包括： </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> 獨特訪客 </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">造訪 </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">發生次數 </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> 頁面檢視 </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">A4T 量度 </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">逗留時間量度 </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">彈回數 </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">反彈率 </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">登入點 </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">退出點 </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">頁面找不到 </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">搜尋 </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">單頁存取次數 </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">單次存取 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: 歸因 IQ 與 Data Workbench 中的歸因有何不同？</b> </p> </td> 
   <td colname="col2"> <p>答: Data Workbench 逐步提供下列功能： </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">歸因更多訪客層級資料來源，例如廣告印象和銷售點。 </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">演算法 (<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html" format="html" scope="external">最適用</a>) 模型。歸因 IQ 僅包括規則模型。 </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">額外的視覺效果，例如<a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html" format="html" scope="external">延遲表格</a>。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: Attribution IQ 可用於資料來源嗎?</b> </p> </td> 
   <td colname="col2"> <p>答: Attribution IQ 目前可用於資料來源，摘要層級資料來源除外。 </p> <p> 這是因為摘要層級資料來源並未與 Analytics 訪客識別碼建立關聯，因此無法使用進階歸因。Attribution IQ 亦支援「交易 ID」資料來源，但用於已啟用<a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html" format="html" scope="external">報表時間處理</a>的虛擬報表套裝時除外。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>問: Attribution IQ 可用於 <a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html" format="html" scope="external">Advertising Analytics</a> 整合嗎?</b> </p> </td> 
   <td colname="col2"> <p>答: 曝光數、成本、點擊、平均位置和平均品質分數等整合量度屬於摘要層級資料來源，因此不相容於 Attribution IQ。然而，與標準 Analytics 事件或量度搭配使用時，中繼資料維度 (如符合類型和關鍵字) 則可用於歸因。 </p> </td> 
  </tr> 
 </tbody> 
</table>


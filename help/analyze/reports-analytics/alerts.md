---
description: 'null'
subtopic: Alerts
title: 警報
topic: Reports and analytics
uuid: e1333a9b-eba0-45b7-b7e6-46e06190db64
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 警報

## 警報 {#concept_8AB25AF6FB52478DB98C1BA4577A2E16}

智慧型警報是所有Adobe Analytics的全新警報系統，可讓您建立和管理警報，並提供警報預覽和規則貢獻。 您可以

* 根據異常 (90％、95％ 或 99％ 臨界值；％ 變化；以上/以下) 建立警報。
* 預覽警報觸發的頻率.
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結.
* 建立在單一警報中擷取多個量度的「堆疊」警報.

您可以在 Report &amp; Analytics 中任何報表內的&#x200B;**[!UICONTROL 更多]** &gt; **[!UICONTROL 警報]**&#x200B;存取此新警報系統。

若要瞭解詳情，請前往 Analysis Workspace 文件內的[智慧型警報](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/intellligent_alerts.html)。

## 新增警報 {#task_51187E8BF19544DDA9EF2057E6F11D35}

說明如何在 Adobe Analytics 中新增警報的步驟。

<!-- 

t_add_an_alert.xml

 -->

導覽至「 **[!UICONTROL Analytics]** &gt;元件」選單中的新 **[!UICONTROL 警報產生器]** 。 不過，您仍可從「Report &amp; Analytics」內的報表進行存取:

1. 在「Report &amp; Analytics」內，開啟您要設定警報的報告。
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.
1. 這步驟將帶您進入[新的警報產生器](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-builder.html)。

## 檢視或編輯現有警報 {#task_2ADF2A05EB784B8BBAFE293AC8243C46}

任務上下文

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]**. 這步驟將帶您進入新的[警報產生器](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/alert-manager.html)。

## 舊式警報遷移 {#concept_7E8179F5EF6E4913B0CE5CF4FF186911}

一些目前的 Analytics 警報功能不會放入將在 2016 年秋季發行的新版警報管理器 (附於 Analysis Workspace 中)。以下表格列出了已廢止的警報功能，以及部分將以不同形式遷移至新版警報管理器的警報功能。

<!-- 

deprecated_alerts.xml

 -->

<table id="table_9307013B16AC4AC7BFC6F4C440FCFDE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 舊式警版功能 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 已廢止或已遷移? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>總計 (所有項目) </p> </td> 
   <td colname="col2"> <p>在維度報表的所有項目上建立警報。 </p> </td> 
   <td colname="col3"> <p>某些情況下，無論您是在維度報表的所有項目上建立警報或只在總體量度本身設定警報 (不套用任何維度)，產生的結果都是一樣。例如，您在「收入」量度建立了每月「所有項目」警報。您也可以透過執行「收入」報表及為其設定每月警報取得相同結果。 </p> <p>在此情況下，舊式「總計 (所有項目)」警報將不再可用並會遷移至較新且較簡單的版本。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排名最前的 1000 個項目 </p> <p> </p> </td> 
   <td colname="col2"> <p>在報表建立排名最前的 1000 個項目警報。 </p> </td> 
   <td colname="col3"> <p>不再可用於新的警報管理器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>以時間為依據的獨特訪客警報 (每日、每週、每月等不重複訪客) </p> <p> </p> </td> 
   <td colname="col2"> <p>建立每小時、每日、每週、每月獨特訪客報表。 </p> </td> 
   <td colname="col3"> <p>在新的警報管理器中，某些以時間為依據的獨特訪客警報將不再受到支援。例如，在您之前能夠設定每日獨特訪客每週警報的地方，您之後將可在獨特訪客量度中設定每日、每週等警報。(Analysis Workspace 支援獨特訪客量度，但不支援每日/每週/每月等獨特訪客量度。) </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜尋 </p> </td> 
   <td colname="col2"> <p>建立已套用搜尋的維度報表警報。只適用於「總計 (「所有項目」)」或「排名最前的 1000 個項目」。 </p> <p> </p> </td> 
   <td colname="col3"> <p>不再可用於新的警報管理器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 針對「Report &amp; Analytics」之報表 </p> </td> 
   <td colname="col2"> <p>為存在於「Report &amp; Analytics」且不對應於 Analysis Workspace 報表的多個報表建立警報，例如 
     <ul id="ul_9A690970A5AE4ED39E664DF23EF3164F"> 
      <li id="li_E2F44EDBA1D945CEBAC4802ED714E7A1">JavaScript </li> 
      <li id="li_B847C6A988854F76824F099681705EC9">路徑長度 </li> 
      <li id="li_4AF656460BC748E8802FAF258D01842F">Bot </li> 
      <li id="li_A300D2803B244774839BEC23D3EB533A">時區 </li> 
      <li id="li_7A0B4CF92F4D47238B7B329EEC213322">頂級網域 </li> 
     </ul> </p> <p> </p> </td> 
   <td colname="col3"> <p>不再可用於新的警報管理器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>參照報表套裝包含 ASI 槽的警報 </p> </td> 
   <td colname="col2"> <p>您將無法再<a href="https://marketing.adobe.com/resources/help/en_US/reference/ASI_slots_admin.html"  >建立或編輯 ASI 槽</a>，同時 ASI 槽將無法在 Analysis Workspace 使用。因此，新的警報將不再支援它們。 </p> <p> </p> </td> 
   <td colname="col3"> <p>不可用於新的警報管理器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用參與率量度的警報 </p> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_participation.html"  >參與率量度</a>可用於「Report &amp; Analytics」，但目前不可用於Analysis Workspace 內的新警報系統。 </p> <p> </p> </td> 
   <td colname="col3"> <p>不可用於新的警報管理器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂日曆報表套裝的每月警報 </p> </td> 
   <td colname="col2"> <p>這只會影響有為報表套裝設定警報，而該報表又有<a href="https://marketing.adobe.com/resources/help/en_US/arb/custom_calendar.html"  >自訂月開始日期</a>之客戶。(全美零售商聯合會/NRF 和自訂日曆類型)。 </p> <p>這並不影響西曆或已修改的西曆報表套裝。這些警報以往是在西曆每月第一天傳送 (例如 1 月 1 日、2 月 1 日等)。這無法與警報新的「異常偵測」功能一起運作，因為此功能會在偵測異常時會以前幾個月的資料作考慮依據。未來，我們會於自訂日曆計劃系統新增支援，讓警報和計劃的專案能在自訂日曆月的第一天傳送，而非只在西曆月的第一天傳送。 </p> <p> </p> </td> 
   <td colname="col3"> <p>尚未可用於新的警報管理器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>從 2015 年 9 月開始未曾運作的警報。 </p> </td> 
   <td colname="col2"> <p>這是警報從 2015 年 9 月開始未曾運作的原因，包括:  </p> 
    <ul id="ul_15812938A2454537AF6ADDB039DE16BC"> 
     <li id="li_D079A819CEE04F609AF18C09EEE83F0D">您在警報管理器的警報上按了「停用」。 </li> 
     <li id="li_E23D01FA0B1341AD8BC1DDD16FB1366F">警報遇到錯誤並永遠無法成功完成。 </li> 
    </ul> <p> </p> </td> 
   <td colname="col3"> 這些警報並不會遷移至新系統。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 標記為「停用」的警報 </td> 
   <td colname="col2"> 現在暫時無法在新的用戶介面停用/重新啟用警報，但我們已有增加此功能性的計劃。 <p> </p> </td> 
   <td colname="col3"> 這些警報並不會遷移至新系統。 </td> 
  </tr> 
 </tbody> 
</table>


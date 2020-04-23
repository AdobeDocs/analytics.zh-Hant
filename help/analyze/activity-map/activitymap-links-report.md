---
description: 「連結」報表會報告目前頁面上找到的連結。 它不會報告為該頁面收集的所有連結。
title: 連結報表
topic: Activity map
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
translation-type: tm+mt
source-git-commit: 6b27755178d156b1eaf159640d466bd84659983d

---


# 連結報表

「連結」報表會報告目前頁面上找到的連結。 它不會報告為該頁面收集的所有連結。

「頁面上的連結」報表提供連結的表格檢視。 有時候，您可能想要在單一檢視中檢視連結點按（或其他量度）的排名。 這可讓您更好地比較一個連結與另一個連結。 建立「頁面上的連結」報表，包括頁面中所有連結（依連結ID）、點按資訊（#和%）及地區的排名清單。 按一下Activity Map工具列中的「頁面中的連結」報表按鈕。

The **[!UICONTROL Links On Page]** report opens below the browser frame in the Activity Map dashboard.

## 標準模式 {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

在標準模式中，「頁面上的連結」報表會顯示從一天到多天的連結資料，並匯總整個日期範圍。 並顯示每個連結的下列資訊：

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 排名 </td> 
   <td colname="col2"> 頁面排名。 在標準模式中，排名值保持不變，而不論您點按的欄為何。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 連結 ID </td> 
   <td colname="col2">The link's primary ID (for more information on how primary ID is defined by the <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">New Link Tracking Methodology</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 點擊次數 </td> 
   <td colname="col2"> 指定連結的原始點按次數及其在頁麵點按總數中所佔的百分比。 如果使用者在工具列中選擇不同的量度，「連結」報表會改為報告該量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地區 </td> 
   <td colname="col2"> 代表連結所在頁面的地區。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可見性 </td> 
   <td colname="col2">與連結的可見性狀態相關。 可能有兩個值： 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>隱藏</b>：連結目前位在頁面中，但未顯示給一般使用者 (類似導覽功能表中的子功能表，只有在使用者將滑鼠暫留到父功能表頂端時才會顯示出來) </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>顯示</b>：連結目前顯示在頁面上。不過，它可能會顯示在下方：使用者必須捲動頁面才能檢視。 </li>
    </ul><p>附註：如果連結設定為「隱藏」，則不會顯示它的覆蓋圖。 </p></td> 
  </tr> 
 </tbody> 
</table>

**篩選資料**

When you want to zero in on a specific link, you can search for a related term in the **[!UICONTROL Filter Data]** field. 只有符合搜尋的連結會有覆蓋圖。 若沒有篩選，則會顯示「 [Activity Map設定」中指](/help/analyze/activity-map/activitymap-overlay-settings.md) 定的覆蓋。

## 即時模式 {#section_AC1967217B5A4532ACB01D33636F6770}

在即時模式中，「頁面上的連結」報表會顯示跨越數分鐘的趨勢資料。

![](assets/links_on_page.png)

<table id="table_61D1FB0F02894055A1AB394DE4FE4742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 排名 </td> 
   <td colname="col2"> 頁面排名。 若是漸層或泡泡覆蓋圖，無論您點按哪一欄，排名值都保持不變。 若是獲益者／損失者覆蓋圖，該排名值會根據哪個連結獲得／損失最多而改變。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 連結 ID </td> 
   <td colname="col2">連結的主要ID。 For more information on how the primary ID is defined by the New <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> Link Tracking Methodology</a>. </td>
  </tr> 
  <tr> 
   <td colname="col1"> 連結點擊次數 </td> 
   <td colname="col2"> 選取時段的點按總數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % 變更 </td> 
   <td colname="col2"> 目前期間連結度量與上一期間連結度量之間的變更百分比。 負%變更以紅色顯示，而正%變更以綠色顯示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 趨勢 </td> 
   <td colname="col2"> 所有收集期間的折線圖。 目前選取的時段會以綠色標籤表示。 目前暫留的時段會以紅色標籤表示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地區 </td> 
   <td colname="col2"> 代表連結所在頁面的地區。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可見性 </td> 
   <td colname="col2">與連結的可見性狀態相關。 可能有兩個值： 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">隱藏：連結目前位在頁面中，但未顯示給您看到 (例如在頁面載入後才會顯示的連結)。 </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">顯示：連結目前顯示在頁面上。不過，它可能會顯示在下方：您必須捲動頁面才能檢視。 </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 排序和篩選 {#section_4B8E8233C21247CAA70DAEC2156548AD}

有時，您只需要分析特定頁面區域的結果（例如左側面板），即可決定如何組織該網頁特定區域的內容。

為此，我們已在「頁面上的連結」報表中建立連結的排序和篩選功能。 篩選可透過篩選欄位使用，搜尋詞將套用至連結ID欄和連結地區欄。 按一下呼叫（排名、連結ID、點按、隨時間變更、地區、可見性）即可排序，並可以是遞增和遞減。 從「頁面上的連結」報表中篩選掉連結時，覆蓋圖會從網站中消失。

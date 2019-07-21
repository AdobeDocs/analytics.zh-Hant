---
description: Adobe Analytics 提供各種「逗留時間」量度和維度。請找出其內容及計算方式。
seo-description: Adobe Analytics 提供各種「逗留時間」量度和維度。請找出其內容及計算方式。
seo-title: 逗留時間
solution: Analytics
title: 逗留時間
topic: 量度
uuid: a9f63da3-7e79-49c3-9b0b-6dcd2aasc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 逗留時間

Adobe Analytics 提供各種「逗留時間」量度和維度。請找出其內容及計算方式。

* [逗留時間量度](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_4F54D70300944748A62088F5870E4B6C)
* [逗留時間維度](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_D51606544CB046FC902E2E317318892C)
* [逗留時間計算方式](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_90A3882638974969A4B8B674FFDB7624)
* [逗留時間常見問題](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_51C2735BACAB42CCBA1DD3CBF238E2F7)
* [計算範例](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_3D63D6A601F34E42AD5366435CB610D5)

## 逗留時間量度 {#section_4F54D70300944748A62088F5870E4B6C}

下表列出各種「逗留時間」量度及其定義，以及可適用於 Adobe Analytics 中的情形。

<table id="table_7095406DF1614F3CAD5E437B919598D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 適用於 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>花費秒數總計 </p> </td> 
   <td colname="col2"> <p>代表訪客與特定維度項目互動的總時間量。 </p> <p>包括值的例項和縱貫後續所有點擊的持續性。如果是 prop，則會對後續連結事件一併計算逗留時間。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder (又稱「總逗留時間」) </p> <p>Data Warehouse </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每次瀏覽逗留時間 (秒數) </p> </td> 
   <td colname="col2"> <p><i>花費秒數總計/(造訪彈回數)</i> </p> <p>代表訪客每次造訪時與特定維度項目互動的平均時間量。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每位訪客逗留時間 (秒數) </p> </td> 
   <td colname="col2"> <p><i>花費秒數總計/(獨特訪客 - 彈回獨特訪客)</i> </p> <p>代表訪客在訪客期限內 (Cookie 的存留時間長度內期間) 與特定維度項目互動的平均時間量。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網站平均逗留時間 (秒數) </p> </td> 
   <td colname="col2"> <p>代表訪客與特定維度項目互動的總時間量，每個序列與一個維度項目互動。這並非單單如其名地只限於「網站」的平均逗留時間。如需有關序列的詳細資訊，請參閱「逗留時間計算方式」一節。 </p> <p>注意: 因為在計算中使用不同的分母，此量度與維度項目層級的「每次瀏覽逗留時間」可能有所差異。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics (以分鐘顯示) </p> <p>Report Builder (以分鐘顯示) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平均頁面逗留時間 </p> </td> 
   <td colname="col2"> <p><b>已停用的量度。</b> </p> <p>我們建議您在需要維度項目的平均時間量時，使用「網站平均逗留時間」。 </p> </td> 
   <td colname="col3"> <p>Report Builder (請求中包含維度時) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工作階段長度總計 </p> <p>(又稱為: 前一個作業長度) </p> </td> 
   <td colname="col2"> <p>僅限於行動應用程式 SDK。針對前一個作業，在下一次應用程式啟動時決定。計算單位為秒，當應用程式在背景中執行時不會計算此量度，只有在使用中才會計算。這是作業層級量度。 </p> <p>例如: 您安裝了應用程式 ABC，啟動後使用了 2 分鐘，然後關閉應用程式。在此作業時間中，不會傳送任何與此應用程式相關的資料。下次啟動應用程式時，將會傳送值為 120 的「工作階段長度總計」。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> <p>Mobile Services UI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平均作業長度 (行動) </p> </td> 
   <td colname="col2"> <p>工作階段長度總計/(啓動-首次啓動) </p> <p>僅限於行動應用程式 SDK。這是作業層級量度。 </p> </td> 
   <td colname="col3"> <p>Report Builder </p> <p>Mobile Services UI </p> </td> 
  </tr> 
 </tbody> 
</table>

## 逗留時間維度 {#section_D51606544CB046FC902E2E317318892C}

下表列出各種「逗留時間」維度及其定義，以及可適用於 Adobe Analytics 中的情形。

<table id="table_BF1B7B8620714105BFB5C1AC37ABE02C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 維度 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
   <th colname="col3" class="entry"> 適用於 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>每次造訪逗留時間 - 精細 </p> </td> 
   <td colname="col2"> <p>將瀏覽時的總逗留時間去除尾數後的為最接近的秒數，適用於可套用至屬於瀏覽一部分的每一次點擊。這是造訪層級維度。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每次瀏覽逗留時間 - 分組 </p> </td> 
   <td colname="col2"> <p>粒度維度分成 9 個不同的範圍。這是造訪層級維度。這些範圍包括: </p> 
    <ul id="ul_BC909A2D22ED4D48A3F7CE6A666F26E5"> 
     <li id="li_0FB28A1F0D894B7C95724A8C6BD5B00B">少於 1 分鐘 </li> 
     <li id="li_10223656420A475AAB3443981D49D10E">1-5 分鐘 </li> 
     <li id="li_0DEE723B81C64EAFB5BD1125D48D3AD2">5-10 分鐘 </li> 
     <li id="li_B736AC970E0049EB8844480702F345A6">10-30 分鐘 </li> 
     <li id="li_21B8ECC3EE66497E8D870A004351B04B">30-60 分鐘 </li> 
     <li id="li_79FB658128FD4F97AAE1A803F1687BD1">1-2 小時 </li> 
     <li id="li_CCC0746FEB954BECB9E670ECCDBF30F3">2-5 小時 </li> 
     <li id="li_BD7AFC524C814F9FAE423A4E301661D4">5-10 小時 </li> 
     <li id="li_C9B5F1A83F99437A98A61756EE286687">10-15 小時 </li> 
     <li id="li_8CC5A279D5804C5EA34C1B3589EF07BA">15 小時以上 </li> 
    </ul> <p>注意: 未依照順序接收點擊時，可能會發生超過 12 小時的造訪。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面逗留時間 - 精細 </p> </td> 
   <td colname="col2"> <p>每次點擊的總逗留時間，去除尾數後為最接近的秒數。這是點擊層級維度，且包含頁面檢視和連結事件。這並非單單如其名地只限於「頁面」維度的逗留時間。 </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面逗留時間 – 分段 </p> </td> 
   <td colname="col2"> <p>粒度維度分成 10 個不同範圍；不過分段的維度只會計算頁面檢視次數 (而排除連結事件)。這是點擊層級維度。這些範圍包括: </p> 
    <ul id="ul_D5F067A2520646A99AA261F9A4625C03"> 
     <li id="li_82307DE66EC548F0AD79DB1505A21F0D">少於 15 秒 </li> 
     <li id="li_585965B82C4D43B6870978A5CE63B5B6">15 至 29 秒 </li> 
     <li id="li_5C20DC78E126472A838818EBA1D954D0">30 至 59 秒 </li> 
     <li id="li_2579C0B9279340ABA3AD4A527D758239">1 至 3 分鐘 </li> 
     <li id="li_E0FD800E948049A48DB4329A3E7A2478">3 至 5 分鐘 </li> 
     <li id="li_D9DBBFE6004F42BD80BB4F9268DF7DA7">5 至 10 分鐘 </li> 
     <li id="li_20F146799679456E8D6434D79EE12C31">10 至 15 分鐘 </li> 
     <li id="li_A38951A553A14AE7A0F23A904EEE35DE">15 至 20 分鐘 </li> 
     <li id="li_D44D773A344E47BFAA771302A49D8BD4">20 至 30 分鐘 </li> 
     <li id="li_8766683DB29147CD8470D2317F750E97">超過 30 分鐘 </li> 
    </ul> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
 </tbody> 
</table>

## 逗留時間計算方式 {#section_90A3882638974969A4B8B674FFDB7624}

Adobe Analytics 使用明確值 (包括連結事件和視訊檢視) 來計算[!UICONTROL 「逗留時間」]。

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. 此外，基於類似的理由，[!UICONTROL 「反彈造訪」](亦即含有單一點擊的[!UICONTROL 「造訪」]) 不會有相關聯的[!UICONTROL 「逗留時間」]。

計算逗留時間時所使用的&#x200B;**「分子」**&#x200B;均為「總逗留秒數」。

**分母**&#x200B;在 Analytics 中不是獨立量度。如果是點擊層級逗留時間量度，分母會是序列。序列是一組連續點擊，其中的指定變數會包含相同的值 (不論是透過設定、擴散或持續)。「擴散」是指為了計算逗留時間，Prop 在頁面檢視之間的持續存在度 (亦即跨越後續連結事件)。

* 例如，如果是[!UICONTROL 「頁面名稱」]或點擊層級的其他維度，基本上分母是[!UICONTROL 「例項」]或[!UICONTROL 「頁面檢視」]，但重新載入和未設定的值 (例如連結事件) 則計為單一互動 (序列)。

* [!UICONTROL 「彈回」]和[!UICONTROL 「退出」]點擊也會從分母中移除，因為無法得知逗留時間。

## 逗留時間常見問題 {#section_51C2735BACAB42CCBA1DD3CBF238E2F7}

<table id="table_D8BA825412B6420390CA78D77A5E57C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 問題 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>是否可以將所有「逗留時間」量度套用至任何維度? </p> </td> 
   <td colname="col2"> <p>以下的「逗留時間」量度可套用至任何維度: </p> 
    <ul id="ul_FC9513D0184B4A74BA1F4CCEA8BC1940"> 
     <li id="li_669156CC549040E08AB4977AF4B8AECB">花費秒數總計 </li> 
     <li id="li_3CCD7E7D127448689228E98A5EE854CB">每次瀏覽逗留時間 (秒數) </li> 
     <li id="li_1F61C157EC414C7F8702BC3F365AA2D7">每位訪客逗留時間 (秒數) </li> 
     <li id="li_A3EF959A9BAB4872915F1A5C1A86D48E">網站平均逗留時間 (秒數) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>哪一個逗留時間維度最適合使用於劃分其他維度項目來劃分? </p> </td> 
   <td colname="col2"> <p>「頁面逗留時間-精細」維度是點擊層級維度。使用由其他維度來劃分這個項目會告訴您當劃分維度也存在時點擊持續的秒數。 </p> <p>在以下範例中，搜尋詞彙「已分類」與 54 秒、59 秒等點擊時間相關聯，可能表示訪客正在花時間閱讀該搜尋詞彙傳回的內容。 </p> <p><img placement="break" align="center"  src="assets/time-spent1.png" id="image_99FB62DCADDA4F8887B14333E65FF8FA" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>哪個量度適合「頁面逗留時間-精細」維度？ </p> </td> 
   <td colname="col2"> <p>任意量度皆可。維度可顯示事件發生時確切點擊的逗留時間。較長的逗留時間表示訪客在事件發生的頁面 (點擊) 上停留較長時間。 </p> <p><img placement="break" align="center"  src="assets/time-spent2.png" id="image_A741C1BA52254124B5C28D030FE20EFF" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">「網站平均逗留時間」</span>和<span class="wintitle">「每次瀏覽逗留時間」</span>有何不同? </td> 
   <td colname="col2"> <p>差異在於量度中的分母: </p> 
    <ul id="ul_E9D7B4D3EDCC4691B2C724E0FE5480D2"> 
     <li id="li_CA34D84A3164473A8737D258425CA468"> <span class="wintitle">「網站平均逗留時間」</span>使用的序列包含了維度項目。 </li> 
     <li id="li_2F2639480BE24927919732D00364EECA"> <span class="wintitle">「每次瀏覽逗留時間」</span>使用瀏覽計次數 </li> 
    </ul> <p>因此，這些量度可能會在造訪層級產生類似的結果，但是在點擊層級就會有所差異。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 計算範例 {#section_3D63D6A601F34E42AD5366435CB610D5}

假設以下幾組伺服器呼叫是針對一次造訪期間內的單一訪客:

<table id="table_63CBB5097E5A46659877E2CA3C94D81C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 造訪點擊編號 </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>造訪間隔時間 (秒數)</b> </td> 
   <td colname="col2"> 0 </td> 
   <td colname="col3"> 30 </td> 
   <td colname="col4"> 80 </td> 
   <td colname="col5"> 180 </td> 
   <td colname="col6"> 190 </td> 
   <td colname="col7"> 230 </td> 
   <td colname="col8"> 290 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>花費秒數</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> 100 </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>點擊類型</b> </td> 
   <td colname="col2"> 頁面 </td> 
   <td colname="col3"> 連結 </td> 
   <td colname="col4"> 頁面 </td> 
   <td colname="col5"> 頁面 </td> 
   <td colname="col6"> 頁面 </td> 
   <td colname="col7"> 頁面 </td> 
   <td colname="col8"> 頁面 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>頁面名稱</b> </td> 
   <td colname="col2"> 首頁 </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> 產品 </td> 
   <td colname="col5"> 首頁 </td> 
   <td colname="col6"> 首頁 <p>(重新載入) </p> </td> 
   <td colname="col7"> 購物車 </td> 
   <td colname="col8"> 訂單確認 </td> 
  </tr> 
 </tbody> 
</table>

### eVar 範例

<table id="table_6D0CF0C53DC145D3A53C06EC3012BCC0">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 造訪點擊編號 </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>eVar1</b> </td> 
   <td colname="col2"> 紅色 <p>(設定) </p> </td> 
   <td colname="col3"> 紅色 <p>(持續) </p> </td> 
   <td colname="col4"> (已過期) </td> 
   <td colname="col5"> 藍色 <p>(設定) </p> </td> 
   <td colname="col6"> 藍色 <p>(設定) </p> </td> 
   <td colname="col7"> 藍色 <p>(持續) </p> </td> 
   <td colname="col8"> 紅色 <p>(設定) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>eVar 花費秒數</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

### prop 範例

<table id="table_1CB4D24A6CAA479C8E59A7C77FFB8226">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 造訪點擊編號 </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>prop1</b> </td> 
   <td colname="col2"> A <p>(設定) </p> </td> 
   <td colname="col3"> A <p>(擴散) </p> </td> 
   <td colname="col4"> (未設定) </td> 
   <td colname="col5"> B <p>(設定) </p> </td> 
   <td colname="col6"> B <p>(設定) </p> </td> 
   <td colname="col7"> A <p>(設定) </p> </td> 
   <td colname="col8"> C <p>(設定) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>prop1 花費秒數</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

根據上表，「逗留時間」量度的計算結果如下:

| prop1 | 花費秒數總計 | 每次瀏覽逗留時間 | 每位訪客逗留時間 | 序列計數 | 網站平均逗留時間 |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| 未歸類的時間 | 100 | - | - | - | - |

| eVar1 | 花費秒數總計 | 每次瀏覽逗留時間 | 每位訪客逗留時間 | 序列計數 | 網站平均逗留時間 |
|---|---|---|---|---|---|
| 紅色 | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| 藍色 | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| 未歸類的時間 | 100 | - | - | - | - |

如果是「逗留時間」維度，相關報表中會顯示以下的資料列:

* 每次瀏覽逗留時間 (粒度): 290
* 頁面逗留時間 (粒度): 10、30、40、50、60、100

可支持此範例的其他附註:

* 所有「逗留時間」均係根據造訪間隔時間 (於造訪的首次點擊從零開始) 計算而得。
* 「花費秒數」是指目前點擊時間戳記與下次點擊時間戳記之間的差距。因此，造訪 (和彈回) 的最後一次點擊沒有逗留時間。
* 「序列」是一組連續點擊，其中的指定變數會包含相同的值 (不論是透過設定、擴散或持續)。例如，prop1「A」有兩個序列: 點擊 1 和 2 以及點擊 6。造訪的最後一次點擊的值不會開始新的序列，因為最後一次點擊沒有逗留時間。網站平均逗留時間會使用序列作為分母。

   * 僅為了計算「逗留時間」的目的，prop 會從頁面點擊「擴散」至後續的連結點擊 (點擊 2 上的 prop1，如上所示)。這得以讓點擊 1 上的 prop1 所設定的值 (「A」) 將逗留時間累積在點擊 2 上。
   * eVar 會將逗留時間累積在 eVar 已設定或持續存在的點擊上。eVar 持續性是由 Analytics「管理控制台」中的 eVar 設定所定義。

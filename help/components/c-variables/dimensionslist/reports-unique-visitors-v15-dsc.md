---
description: 顯示存取您的網站的獨特訪客人數。每位訪客會被記錄一次，不論此人瀏覽網站多少次。
title: 不重複訪客
topic: Reports
uuid: e70e1a14-b3b9-4d1a-a8a5-a247a443c752
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 不重複訪客

顯示存取您的網站的獨特訪客人數。每位訪客會被記錄一次，不論此人瀏覽網站多少次。

**資料範例**

請在下表中參閱此頁面的範例。以下顯示的是相同訪客:

<table id="table_4F54873A4ED8451494E466C2BDB15B00"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 1/1/2017 </th> 
   <th colname="col3" class="entry"> 1/1/2017 </th> 
   <th colname="col4" class="entry"> 1/2/2017 </th> 
   <th colname="col5" class="entry"> 1/2/2017 </th> 
   <th colname="col6" class="entry"> 1/2/2017 </th> 
   <th colname="col7" class="entry"> 1/3/2017 </th> 
   <th colname="col8" class="entry"> 1/4/2017 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>頁面 </p> </td> 
   <td colname="col2"> <p>A </p> </td> 
   <td colname="col3"> <p>C </p> </td> 
   <td colname="col4"> <p>A </p> </td> 
   <td colname="col5"> <p>B </p> </td> 
   <td colname="col6"> <p>C </p> </td> 
   <td colname="col7"> <p>D </p> </td> 
   <td colname="col8"> <p>E </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eVar </p> </td> 
   <td colname="col2"> <p>T, U </p> </td> 
   <td colname="col3"> <p>V </p> </td> 
   <td colname="col4"> <p>W </p> </td> 
   <td colname="col5"> <p> </p> </td> 
   <td colname="col6"> <p>X, Y </p> </td> 
   <td colname="col7"> <p>Z </p> </td> 
   <td colname="col8"> <p>Z </p> </td> 
  </tr> 
 </tbody> 
</table>

## 獨特訪客報告 - 趨勢量度 {#section_372C08A881D34BBF811C1DE0A1460617}

[!UICONTROL 獨特訪客]報表顯示行為的方式與 Ad Hoc Analysis 類似。對於產生瀏覽的每次點擊，都會計入該次點擊的訪客。每個頁面都會因為有該訪客在頁面上而獲得評分。

<table id="table_7D9119045E8243698B6BB2E8C93F6B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 頁面 </th> 
   <th colname="col2" class="entry"> 不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

同樣地，每個日期都會因為當天有該訪客而獲得評分。

<table id="table_E0D06D9434444947BDA818F61A580B65"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL 獨特訪客報表]劃分依據&#x200B;*`Page`*。**

您可以為[!UICONTROL 獨特訪客報告]選取頁面。在下列報告中，訪客於下列日期瀏覽頁面 A:

<table id="table_2ABA17B19E0D4F92AAB003BE784DA9E0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 以時段為基礎的獨特訪客 (趨勢) {#section_B3502EBF1ACB487AA8E0EFBA9A0561FD}

您可以執行每小時、每日、每週、每月、每季和每年的[!UICONTROL 獨特訪客報告] (趨勢)。

以時段為基礎的獨特訪客只會在指定時段內的第一次瀏覽時被計數。例如，「每小時獨特訪客」會在指定時數內的第一次瀏覽時被計數。「每日獨特訪客」則會在指定的那一天內第一次瀏覽時被計數。

<table id="table_FF14F05CDFDA4F2E92A62D9D751A1CAA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 每週不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

針對「每日獨特訪客」會顯示下列報告。

<table id="table_4E44BC4722064501A5B648BE80ED8E60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 每日不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>4 </p> </td> 
  </tr> 
 </tbody> 
</table>

量度總計會隨著報告的日期範圍而變更。行銷報告會從日期範圍的開始時間起計算以時間為基礎的唯一訪客。例如，若日期範圍為 1 月 2 日到 1 月 3 日，則會針對「每週獨特訪客」顯示下列結果:

<table id="table_B695708BB22949E7BA293FE492D2EEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 每週不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

**區段**

您可以透過區段來變更日期範圍，以納入較晚的日期，而非較早的日期。例如，假設日期範圍仍是 1 月 2 日到 1 月 3 日 (如上表所示)。若您套用「頁面 = C」的區段，則 1 月 2 日將不在此區段中，「每週獨特訪客」的第一次點擊會發生在 1 月 3 日。若您改為套用「頁面 = D」的區段，則 1 月 2 日與 1 月 3 日都將被排除。「每週獨特訪客」不會有任何顯示結果，且將排除在總計外。

**以時段為基礎的獨特訪客報告**

這些報告會使用特定頁面、prop 與屬性 (範例: 頁面 = A)。

假設您要使用以時段為基礎的「獨特訪客」量度建立[!UICONTROL 頁面報告]的趨勢。若為以時段為基礎的「唯一訪客」報告選取了劃分或變數，行銷報告將會計入訪客和屬性配對的所有唯一例項。就訪客的第一次點擊而言，此處理方式與前述範例並無不同。對於後續的點擊，這些報告會納入前述報告未納入的點擊 (若頁面不同)。

對於「頁面 = A」的「每週唯一訪客」，行銷報告會從總計中排除 1 月 2 日。之所以會加以排除，是因為行銷報告已在 1 月 1 日計入「每週唯一訪客」。以下是「頁面 = A」的每週獨特訪客報告:

<table id="table_9C5E00029C7340B28D76696E84F66511"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 每週不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

就「頁面 = B」的每週獨特訪客而言，唯一發生的日期為 1 月 2 日，如下所示:

<table id="table_262150BECCB74120B58F506F4BC6F629"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日期 </th> 
   <th colname="col2" class="entry"> 瀏覽 - 每週獨特訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 非趨勢報告上以時段為基礎的獨特訪客量度 {#section_90B784F4E49F4930B3F0923B95958BA2}

您可以在非趨勢報告上新增以時段為基礎的獨特訪客量度，例如[!UICONTROL 頁面報告]上的「每週獨特訪客」量度。

<table id="table_8651A42696B0404CAEAE0FC5522CC1C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 頁面 </th> 
   <th colname="col02" class="entry"> 瀏覽日期 </th> 
   <th colname="col2" class="entry"> 瀏覽 - 每週獨特訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col02"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E </p> </td> 
   <td colname="col02"> <p>5 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col02"> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 頁面報告]上的「每日獨特訪客」量度會顯示:

<table id="table_04C7C305C2B945D6A79A6B80F48A4BF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 頁面 </th> 
   <th colname="col02" class="entry"> 瀏覽日期 </th> 
   <th colname="col2" class="entry"> 瀏覽 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col02"> <p>1 年 1 月 </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col02"> <p>2 年 1 月 </p> </td> 
   <td colname="col2"> <p>2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col02"> <p>3 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col02"> <p>4 年 1 月 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col02"> <p> </p> </td> 
   <td colname="col2"> <p>4 個每日獨特訪客 </p> </td> 
  </tr> 
 </tbody> 
</table>

若要依某個屬性來劃分另一個屬性 (例如依 *`page`* 劃分 *`eVar`*)，Analytics 會為時段與頁面 (或相關聯的屬性) 的每個唯一例項分配一個以時段為基礎的獨特訪客。

若您依 eVar T、U 來劃分「頁面 A」，則會排除 1 月 2 日，因為「頁面 A」是在 1 月 1 日檢視的。針對「每週獨特訪客」會顯示下列結果:

<table id="table_328A6F2E920A44B3B55A6E6A630F6DBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> eVar </th> 
   <th colname="col2" class="entry"> 每週不重複訪客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>T </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>U </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總計 </p> </td> 
   <td colname="col2"> <p>1 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 永久性 Cookie {#section_81E139F08AEB4E30A06472856975EA1E}

瀏覽之間使用的永久性 Cookie 會保留在訪客的電腦上，以便 Adobe 可以在後續的瀏覽中識別訪客。若要瞭解使用者接受或拒絕永久性 Cookie 的百分比，請選取&#x200B;**[!UICONTROL 「篩選]** &gt; **[!UICONTROL 永久性 Cookie」]**。

下方的圖形與詳細資料檢視，可顯示永久性 Cookie 訪客與非永久性 Cookie 訪客的數量。通常來說，非永久性 Cookie 訪客的數量都可忽略不計。

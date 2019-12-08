---
description: 您可以自訂報表的傳送計劃。您可以在特定時間停止傳送，也可以指定某一報表的傳送次數。新計劃會使用報表中定義的日期範圍。例如，如果您針對最近 90 天建立了報告，並排程讓其每天執行，則會每天收到最近 90 天的報告。如果您是從日曆的靜態日期範圍建立報表，則每次報表傳送時，您看到的都是相同的報表。
title: 計劃管理員
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 計劃管理員

您可以自訂報表的傳送計劃。您可以在特定時間停止傳送，也可以指定某一報表的傳送次數。新計劃會使用報表中定義的日期範圍。例如，如果您針對最近 90 天建立了報告，並排程讓其每天執行，則會每天收到最近 90 天的報告。如果您是從日曆的靜態日期範圍建立報告，則每次報告傳送時，您看到的都是相同的報告。

## 計劃管理員 {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

您可以自訂報表的傳送計劃。您可以在特定時間停止傳送，也可以指定某一報表的傳送次數。新計劃會使用報表中定義的日期範圍。例如，如果您針對最近 90 天建立了報告，並排程讓其每天執行，則會每天收到最近 90 天的報告。如果您是從日曆的靜態日期範圍建立報告，則每次報告傳送時，您看到的都是相同的報告。

> [!NOTE] 當使用者帳戶停用時，該使用者建立的任何計畫報表傳送都會暫停。

若要確保劃分中的明細項目在儲存和排程報表中持續存在，請使用「表格產生器」中的「編輯項目 ****[](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) 」功能，在劃分中建立固定維度清單。

>[!IMPORTANT]
>
>「臨機分析」可讓您快速定義並排程報表，以符合特定、及時的臨機報告需求。 其設計目的並不是要完整匯出大量的列、欄、量度評估的資料，也不是使用資料擷取來進行廣泛的劃分。
>
>「Ad Hoc Analysis」中計劃報表的實際限制是根據下列原則: 如果您的報表未在 10 分鐘內建立 (Ad Hoc Analysis 的逾時值)，則代表您的報表可能太複雜了。
>
>最可能的原因是報表中有太多量度、太多維度元素劃分、太多列或欄，或其他極端狀況，使得「Ad Hoc Analysis」的報表產生程序過於耗時。這種報表應在「Data Warehouse」中執行，這是 Adobe Analytics 專為離線執行的完整資料擷取以及可能需時數小時至數天的報表產生程序所打造的功能。
>
>例如，「Ad Hoc Analysis」可以處理 50,000 列的資料，但依據 10 種瀏覽器類型劃分這些資料等於 50,0000 乘以 10，這對於 Ad Hoc Analysis 報告工具來說是過於複雜的指數型暴增。更多的劃分會讓資料列再度呈現倍數增加。請為包含上述所有因素，但在嚴格條件內無法定義的「Ad Hoc Analysis」報告，定義要限制的實際數目或列、欄和劃分。

## 計劃傳送報表 {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

說明如何計劃傳送報表的步驟。

<!-- 

t_schedule_delivery.xml

 -->

1. Click **[!UICONTROL Tools]**, then click **[!UICONTROL Schedule Manager]**.
1. 在[!UICONTROL 計劃管理員]**上按一下[!UICONTROL 新增。]**

## 傳送選項 - 定義 {#reference_CA49AC560258471AAE959BCA243F170C}

傳送選項的設定定義。

<!-- 

r_delivery_options.xml

 -->

您可將目前選取報表中顯示的資訊，以您選取的格式進行傳送。您可一次傳送或設定傳送計劃，並指定喜好的檔案格式。您可建立並傳送數位簽名來向檔案收件人保證該檔案的可靠性。您可將檔案發送至電子郵件地址或將其上載至 FTP 伺服器。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>欄位 </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>名稱 </p> </td> 
   <td colname="col2"> <p> 此報表的可設定名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>告知報表 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 檔案格式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: 將報表輸出為試算表，包括所有影像。可在 Microsoft Excel 中進行編輯。 </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: 將報表輸出為逗號分隔值。可在簡單的文字編輯器 (如記事本) 或試算表編輯器 (如 Excel) 中進行編輯。不包含任何影像。 </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: 將報表輸出為「可攜式文件格式」。無法編輯，可在 Adobe Acrobat 或 Adobe Reader 中進行檢視。 </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: 將報表輸出為「超文字標記語言」附件。這是大部分網站的組成格式。無法編輯 (除非您熟悉 HTML 程式碼)。 </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: 將報表輸出為 RTF 格式，包括所有影像。可在 Microsoft Word 或 WordPad 中進行編輯。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 進階 </p> </td> 
   <td colname="col2"> <p> See <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案目標 </p> </td> 
   <td colname="col2"> <p>電子郵件: 透過電子郵件傳送的設定。 </p> <p>FTP: 上載至 FTP 伺服器的設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報表範圍和傳送計劃 </p> </td> 
   <td colname="col2"> <p>指定何時傳送報表。新計劃會使用報表中定義的日期範圍。例如，如果您針對最近 90 天建立了報告，並排程讓其每天執行，則會每天收到最近 90 天的報告。如果您是從日曆的靜態日期範圍建立報告，則每次報告傳送時，您看到的都是相同的報告。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 進階格式設定 - 定義 {#reference_F99B65BF7C9746638D8147EED147015B}

「進階格式設定」的設定定義。

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>欄位 </p> </th> 
   <th colname="col2" class="entry"> <p>定義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>檔案名稱 </p> </td> 
   <td colname="col2"> <p>使用者定義的檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將 ID 附加到檔案名 </p> </td> 
   <td colname="col2"> <p>自動附加報表 ID 至檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 將日期附加到檔案名 </p> </td> 
   <td colname="col2"> <p> 自動附加報表日期至檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>語言 </p> </td> 
   <td colname="col2"> <p> 可讓您選取報表的語言。無論您使用何種語言，您皆可透過下述任一語言傳送報表:  </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">英文 </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">西班牙文 </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">簡體中文 </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">繁體中文 </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">法文 </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">德文 </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">日文 </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">葡萄牙文 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>編碼 </p> </td> 
   <td colname="col2"> <p>指定編碼類型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 以壓縮檔案傳送報表 </p> </td> 
   <td colname="col2"> <p> 壓縮檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳送數位簽名檔案 </p> </td> 
   <td colname="col2"> <p>建立數位簽名，與電子郵件一併傳送。 </p> </td> 
  </tr> 
 </tbody> 
</table>


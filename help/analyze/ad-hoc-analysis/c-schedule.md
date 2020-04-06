---
description: 您可以自訂報表的傳送排程。 您可以在特定時間停止傳送，或指定您要傳送報表的次數。 新排程會使用報表中定義的日期範圍。例如，如果您建立最近90天的報表並排程它每天執行，則您每天會收到最近90天的報表。 如果您從日曆建立具有靜態日期範圍的報表，則每次傳送報表時，您都會看到相同的報表。
title: 計劃管理員
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 計劃管理員

您可以自訂報表的傳送排程。 您可以在特定時間停止傳送，或指定您要傳送報表的次數。 新排程會使用報表中定義的日期範圍。例如，如果您建立最近90天的報表並排程它每天執行，則您每天會收到最近90天的報表。 如果您從日曆建立具有靜態日期範圍的報表，則每次傳送報表時，您都會看到相同的報表。

## 計劃管理員 {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

您可以自訂報表的傳送排程。 您可以在特定時間停止傳送，或指定您要傳送報表的次數。 新排程會使用報表中定義的日期範圍。例如，如果您建立最近90天的報表並排程它每天執行，則您每天會收到最近90天的報表。 如果您從日曆建立具有靜態日期範圍的報表，則每次傳送報表時，您都會看到相同的報表。

>[!NOTE] 使用者帳戶遭停用後，系統會暫停該使用者建立的任何報表傳送計劃。

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Ad Hoc Analysis 可讓您根據即時、臨機的特定需求，迅速定義及排程報表。它不適用於使用資料擷取完整匯出大量資料或列、欄、量度評估或廣泛劃分。
>
>「Ad Hoc Analysis」中計劃報表的實際限制是根據下列原則：如果您的報表未在 10 分鐘內建立 (Ad Hoc Analysis 的逾時值)，則代表您的報表可能太過複雜。
>
>您的報表最有可能有太多量度、太多維度元素劃分、太多列或欄，或其他極端情況，使臨機分析的報表產生程式過長。 此類報表必須在資料倉庫中執行，Adobe Analytics是一項功能，可讓您離線執行完整資料擷取，並產生報表，需花費數小時或數天。
>
>例如，臨機分析可處理50,000列資料，但將十種瀏覽器類型的資料劃分為50,000乘以10，這對臨機報告工具而言可能過於複雜。 其他劃分會以指數級方式增加資料列。 為臨機分析報告定義要限制的實際數目或列、欄和劃分無法以明確的辭彙定義，但是這些因素的組合。

## 排程傳送報表 {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

說明如何傳送報表的排程步驟。

<!-- 

t_schedule_delivery.xml

 -->

1. 按一 **[!UICONTROL Tools]**&#x200B;下，然後按一 **[!UICONTROL Schedule Manager]**&#x200B;下。
1. 在上， [!UICONTROL Schedule Manager]按一下 **[!UICONTROL New.]**

## 傳送選項 - 定義 {#reference_CA49AC560258471AAE959BCA243F170C}

「傳送選項」設定的定義。

<!-- 

r_delivery_options.xml

 -->

您可以將目前選取報表中顯示的資訊，傳送至您選取的格式。 您可以一次傳送或設定傳送排程，並指定您偏好的檔案格式。 您可以建立並傳送數位簽章，以確保檔案的接收者是正版的。 您可以將檔案傳送至電子郵件地址或上傳至FTP伺服器。

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
   <td colname="col2"> <p>告訴您報表ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 檔案格式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel：將報表輸出為試算表，包括所有影像。可在Microsoft Excel中編輯。 </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV：將報表輸出為逗號分隔值。可在簡單的文字編輯器（例如記事本）或試算表編輯器（例如Excel）中編輯。 不包含任何影像。 </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF：將報表輸出為「可攜式文件格式」。不可編輯，且可在Adobe Acrobat或Adobe Reader中檢視。 </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML：將報表輸出為「超文字標記語言」附件。此格式是大部分網站的組成部分。 除非您熟悉HTML程式碼，否則無法編輯。 </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word：將報表輸出為 RTF 格式，包括所有影像。可在Microsoft Word或WordPad中編輯。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 進階 </p> </td> 
   <td colname="col2"> <p> 請參閱<a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   >進階格式設定</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>檔案目標 </p> </td> 
   <td colname="col2"> <p>電子郵件：透過電子郵件傳送的設定。 </p> <p>FTP：上載至 FTP 伺服器的設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>報表範圍和傳送排程 </p> </td> 
   <td colname="col2"> <p>指定何時傳送報表。 新排程會使用報表中定義的日期範圍。例如，如果您建立最近90天的報表並排程它每天執行，則您每天會收到最近90天的報表。 如果您從日曆建立具有靜態日期範圍的報表，則每次傳送報表時，您都會看到相同的報表。 </p> </td> 
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
   <td colname="col2"> <p>用戶定義的檔案名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將ID附加至檔案名稱 </p> </td> 
   <td colname="col2"> <p>自動將報表ID附加至檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 將日期附加至檔案名稱 </p> </td> 
   <td colname="col2"> <p> 自動將報表的日期附加至檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>語言 </p> </td> 
   <td colname="col2"> <p> 可讓您選取報表的語言。 無論您使用何種語言，您皆可透過下述任一語言傳送報表： </p> 
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
   <td colname="col2"> <p>建立數位簽名，以便隨電子郵件傳送。 </p> </td> 
  </tr> 
 </tbody> 
</table>


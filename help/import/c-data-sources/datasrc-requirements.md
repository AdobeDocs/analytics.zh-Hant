---
description: 有關使用資料來源前的報表套件需求資訊。
subtopic: Data sources
title: 需求和上傳限制
topic: Developer and implementation
uuid: d79fca77-fa0e-4171-b978-cdee5c67d9df
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 需求和上傳限制

有關使用資料來源前的報表套件需求資訊。

下列各節列出資料來源和匯入行銷報表與分析之資料的限制。

* [大小限制](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [日期](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [一般](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [多位元組支援](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [上傳網站記錄檔](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## 大小限制 {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* 每個 FTP 帳戶中所有檔案的資料總限制是 50 MB。如果大小超過 50 MB 就會暫停處理，直到大小總計低於 50 MB 才會繼續。

## 日期 {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* 在單一天之中，僅限上傳 90 天不同日期的資料。如果超過此限制，上傳會失敗，並出現錯誤訊息，指出您已超過最大不同日期。
* 系統僅可匯入包含目前或過去日期的資料。請勿在資料來源資料中使用未來的日期。
* 必須對所有列指定要啟用報表製圖功能的日期。如果列不包含日期，資料來源會產生錯誤並拒絕檔案。日期/時間格式依資料來源類型而異:

   * **完全處理資料來源**:使用ISO 8601日期格 `YYYY-MM-DDThh:mm:ss±UTC_offset` 式(例如 `2013-09-01T12:00:00-07:00`)或Unix時間格式（自1970年1月1日以來經過的秒數）。

   * **標準與整合資料來源**:使用下列日期格式： `MM/DD/YYYY/HH/mm/SS` (例如 `01/01/2013/06/00/00`)

## 一般 {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* 上傳資料來源檔案時，資料來源會執行基本資料驗證，確定檔案不包含格式錯誤。若在檔案中發現錯誤，會傳送電子郵件通知並停止處理。
* 資料欄位不可包含分號。資料來源會略過包含分號的記錄。
* 來自網站記錄檔、流量的資料以及部分通用資料來源群組，在資料倉儲或 Discover 中無法使用。有關詳細資訊，請參閱[資料類型與類別](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md)。
* 資料來源不支援序列化事件。

## 多位元組支援 {#section_96C8D26B21184C3E839865DB6F23EA22}

資料來源支援多位元組編碼。資料來源會嘗試偵測傳入資料來源檔案的格式，並在必要時將其轉換為支援的格式。下表列出常見的字元格式及其支援狀態。

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字元格式 </th> 
   <th colname="col2" class="entry"> 支援 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>支援。資料來源使用的報表套裝必須啟用對多位元組字元的支援。 </p> <p>請參閱「說明」中的「<a href="https://marketing.adobe.com/resources/help/en_US/reference/new_report_suite.html"  >新增報表套裝</a>」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-8 with Byte Order Mark (EF BB BF) </td> 
   <td colname="col2"> <p>支援。此格式為非標準格式，但許多 Windows 應用程式以此格式儲存。 </p> <p>例如，如果您選擇「UTF-8」，WordPad 會儲存為該格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1 (又叫做 Latin-1 或 Windows-1252) </td> 
   <td colname="col2"> 支援。當您選擇「定位點分隔」匯出時，Microsoft Excel 會儲存為該格式。報表套裝必須使用 ISO-8859-1 地區設定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Little-endian, with Byte Order Mark (FF FE) </td> 
   <td colname="col2"> 轉換為 ISO-8859-1 或 UTF-8，由您的報表套裝設定決定。當您選擇「Uunicode」匯出時，Microsoft Excel 會儲存為該格式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Big-endian, with Byte Order Mark (EF FF) </td> 
   <td colname="col2"> 轉換為 ISO-8859-1 或 UTF-8，由您的報表套裝設定決定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 with no byte-order mark </td> 
   <td colname="col2"> 不支援。 </td> 
  </tr> 
 </tbody> 
</table>

若您提交 UTF-8 或 ISO-8859-1 檔案，而您沒有將報表套裝設定為支援它，會發生下列情況之一:

* 在轉換過程中偵測到錯誤，此時您將得到一則訊息，如「從 UTF-8 轉換到 ISO-8859-1 時在檔案中的位置 18 發現錯誤字元」。
* 檔案處理過程中未出現錯誤，但您會在報表中發現亂碼。

## 上傳網站記錄檔 {#section_DD736FC971FE45C89AB310BEDC1FE707}

* 檢視網站記錄時，最實用的報表是流量報表，如頁面檢視。
* 顯示的頁面名稱為整個 URL，包括查詢字串。
* 每個檔案請求以單獨的頁面檢視出現，包括樣式表和影像檔。
* 若您附加資訊到 URL，檔案可能會被記錄為單獨的頁面。例如，行銷報表記錄會將下列 URL 記錄為兩個單獨頁面：

[!DNL /jokes/misc/snail_joke.html?userid=12345]

[!DNL /jokes/misc/snail_joke.html?userid=98765]

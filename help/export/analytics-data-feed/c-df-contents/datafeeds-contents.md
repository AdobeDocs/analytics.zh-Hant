---
description: 本節說明資料饋送傳送中所含的檔案。
keywords: 資料饋送；工作；內容；資訊清單；檔案；查閱；點擊資料；傳送內容
seo-description: 本節說明資料饋送傳送中所含的檔案。
seo-title: 資料饋送內容-總覽
solution: Analytics
subtopic: 資料饋送
title: 資料饋送內容-總覽
topic: Reports & Analytics
uuid: 82a86314-4841-4133-a0 dc-4e7 c6 cd14 fc1
translation-type: tm+mt
source-git-commit: 7fe23291d8ee9675181065025692108aee3ea9a5

---


# 資料饋送內容-總覽

本節說明資料饋送傳送中所含的檔案。

## 資訊清單檔案 {#section_044BBDE2906D49518F8264CD4832D429}

資訊清單檔案包含上傳資料集內每個檔案的下列詳細資料:

* 檔案名稱
* 檔案大小
* MD5 雜湊
* 檔案中包含的記錄數

資訊清單檔案的格式與 Java JAR 資訊清單檔案相同。

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. 資訊清單檔案的命名方式如下:

```
<report_suite_id>_YYYY_MM_DD.txt
```

典型的資訊清單檔案包含類似下列的資料:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

每個資訊清單檔案包含標題，指出查閱檔案總數、資料檔案以及所有資料檔案中的記錄總數。此標題之後有多個區段，包含資料饋送傳送中每個檔案的相關資訊。

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## 查閱檔案 {#section_B5863537A48D47D78D0F7274838923C1}

查閱檔案不含點擊資料，它們是提供點擊資料欄標題的補充檔案，以及將資料饋送中找到的 ID 轉譯為實際值的查閱檔案。例如，瀏覽器欄中的 "497" 值指出點擊來自 "Microsoft Internet Explorer 8"。

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. `browser.tsv` 等其他檔案則是一般檔案。

查閱檔案會以壓縮的 zip 檔案一起傳送，命名方式如下:

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
```

* [!DNL column_headers.tsv] (針對此資料饋送而自訂)
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv] (針對此資料饋送而自訂)

## 點擊資料檔案 {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. 此檔案中的資料量由傳送格式決定 (每小時或每日、單一檔案或多個檔案)。此檔案僅包含點擊資料。欄標題則與查閱檔案一同傳送。此檔案的每一行包含單一伺服器呼叫。

## 傳送內容 {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>檔案使用ISO-8859-1編碼。

Adobe 傳送的實際檔案不一，取決於您設定的資料饋送類型而定。請從下表中符合您資料饋送的設定，找出傳送檔案的說明。

檔案名稱中指出的時間 (HHMMSS) 一律表示檔案中資料的日期範圍開頭，與檔案的產生或上傳時間無關。

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 傳送格式 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 每日、單一檔案 </td> 
   <td colname="col2"> <p>收集一天的資料後，您會收到包含下列項目的傳送內容: </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">單一壓縮資料檔案。 </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">資訊清單檔案。 </li> 
    </ul> <p>資料檔案的傳送名稱如下: </p> 
    <code>&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;。&lt;compression_suffix&gt;
    </code> <p> 其中 <code>&lt;compression_suffix&gt;</code> 是 <code>tar.gz</code> 或 <code>zip</code>。 </p> <p>提取之後，資料檔案包含單一 <span class="filepath">hit_data.tsv</span> 檔案 (內含當天所有資料)，以及如上所述的壓縮查閱檔案。 </p> <p>點擊資料檔案大小不一，主要取決於目前使用的變數數目以及報表套裝的流量總量。不過，平均而言，一行資料約為 500B (壓縮) 或 2KB (解壓縮)。將此值乘以伺服器呼叫數目，可提供資料饋送檔案的大小粗估。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每日、多個檔案 </td> 
   <td colname="col2"> <p>收集一天的資料後，您會收到包含下列項目的傳送內容: </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">分割為 2 GB 區塊的一或多個壓縮資料檔案。 </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">資訊清單檔案。 </li> 
    </ul> <p>每個資料檔案的傳送名稱如下: </p> 
    <code>&lt; index&gt;-&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;。&lt;compression_suffix&gt;
    </code> <p> 其中 <code>&lt;index&gt;</code> 是從 <i>1</i> 到 <i>n</i> 的遞增檔案索引 (假設有 <i>n</i> 個檔案_，而 <code>&lt;compression_suffix&gt;</code> 是 <code>tar.gz</code> 或 <code>zip</code>。 </p> <p>提取之後，每個資料檔案包含單一 <span class="filepath">hit_data.tsv</span> 檔案 (內含大約 2 GB 的解壓縮資料)，以及如上所述的壓縮查閱檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每小時、單一檔案 </td> 
   <td colname="col2"> <p>收集一小時的資料後，您會收到包含下列項目的傳送內容: </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">單一資料檔案。 </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">資訊清單檔案。 </li> 
    </ul> <p>資料檔案的傳送名稱如下: </p> 
    <code>&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;-&lt; HHMSS&gt;。&lt;compression_suffix&gt;
    </code> <p> 其中 <code>&lt;compression_suffix&gt;</code> 是 <code>tar.gz</code> 或 <code>zip</code>。 </p> <p>提取之後，資料檔案包含單一 <span class="filepath">hit_data.tsv</span> 檔案，內含該小時的所有資料。上述的壓縮查閱檔案傳送時僅包含每天第一個小時的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每小時、多個檔案 </td> 
   <td colname="col2"> <p>收集一小時的資料後，您會收到包含下列項目的傳送內容: </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">分割為 2 GB 區塊的一或多個壓縮資料檔案。 </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">資訊清單檔案。 </li> 
    </ul> <p>每個資料檔案的傳送名稱如下: </p> 
    <code>&lt; index&gt;-&lt; report_ suite&gt;_&lt; YYYY-mm-dd&gt;-&lt; HHMSS&gt;. tsv。&lt;compression_suffix&gt;
    </code> <p>其中 <code>&lt;index&gt;</code> 是從 <i>1</i> 到 <i>n</i> 的遞增檔案索引 (假設有 <i>n</i> 個檔案，而 <code>&lt;compression_suffix&gt;</code> 是 <code>gz</code> 或 <code>zip</code>。 </p> <p>提取之後，每個資料檔案包含單一 <span class="filepath">hit_data.tsv</span> 檔案，內含大約 2 GB 的解壓縮資料。上述的壓縮查閱檔案傳送時僅包含每天第一個小時的資料。 </p> </td> 
  </tr> 
 </tbody> 
</table>


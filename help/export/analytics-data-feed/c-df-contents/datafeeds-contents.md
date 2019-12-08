---
description: 本節說明資料饋送傳送中所含的檔案。
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
subtopic: data feeds
title: 資料摘要內容 - 概觀
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料摘要內容 - 概觀

本節說明資料饋送傳送中所含的檔案。

## 資訊清單檔案

資訊清單檔案包含上傳資料集內每個檔案的下列詳細資料:

* 檔案名稱
* 檔案大小
* MD5 雜湊
* 檔案中包含的記錄數

資訊清單檔案的格式與 Java JAR 資訊清單檔案相同。

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. 資訊清單檔案的命名方式如下:

```text
[rsid]_[YYYY-mm-dd].txt
```

典型的資訊清單檔案包含類似下列的資料:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

每個資訊清單檔案包含標題，指出查閱檔案總數、資料檔案以及所有資料檔案中的記錄總數。此標題之後有多個區段，包含資料饋送傳送中每個檔案的相關資訊。

Some feeds are configured to receive a `.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## 查閱檔案

有些資料饋送欄會輸出與其實際值對應的數字。 查閱檔案可用來比對資料饋送欄中的數字，並比對它與實際值。 例如，點擊資料欄中的值為"497" `browser` ，表示如果您檢視，點擊來自"Microsoft Internet Explorer 8" `browser.tsv`。

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. `browser.tsv` 等其他檔案則是一般檔案。

查閱檔案會以壓縮的 zip 檔案一起傳送，命名方式如下:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
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

## 點擊資料檔案

Hit data is provided in a [!DNL hit_data.tsv] file. 此檔案中的資料量由傳送格式決定 (每小時或每日、單一檔案或多個檔案)。此檔案僅包含點擊資料。欄標題則與查閱檔案一同傳送。此檔案的每一行包含單一伺服器呼叫。

Adobe傳送的檔案會因您設定的資料饋送類型而有所不同。 所有檔案都使用ISO-8859-1編碼。

* `[rsid]` 是指資料饋送的報表套裝ID。
* `[index]` 僅用於多個檔案饋送，並參照已編頁檔案的正確順序。
* `[YYYY-mm-dd]` 指資料饋送的開始日期。
* `[HHMMSS]` 僅用於每小時動態消息，且是指資料動態消息的開始時數。
* `[compression_suffix]` 是指使用的壓縮類型。 通常資料饋送會壓縮至 `tar.gz` 或檔 `zip` 案中。

### 每日、單一檔案

收集一天的資料後，您會收到單一壓縮資料檔案和資訊清單檔案。 資料檔案的名稱為：

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取後，資料檔案會包含單一檔案， `hit_data.tsv` 其中包含當天的所有資料，以及任何必要欄的查閱檔案。

### 每日，多個檔案

收集一天的資料後，您會收到一或多個壓縮資料檔案和資訊清單檔案。 資料檔案的名稱為：

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

提取後，每個資料檔案都包含一 `hit_data.tsv` 個包含約2GB未壓縮資料的檔案，以及任何必要欄位的查閱檔案。

### 每小時、單一檔案

在收集資料一小時後，您會收到單一壓縮資料檔案和資訊清單檔案。 資料檔案的名稱為：

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

提取後，資料檔案會包含單一檔案， `hit_data.tsv` 其中包含該小時的所有資料，以及任何必要欄的查閱檔案。

### 每小時、多個檔案

在收集資料一小時後，您會收到一或多個壓縮資料檔案和資訊清單檔案。 資料檔案的名稱為：

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

提取後，每個資料檔案都包含一 `hit_data.tsv` 個包含約2GB未壓縮資料的檔案，以及任何必要欄位的查閱檔案。

## 資料檔案大小

點擊資料檔案大小會根據目前使用的變數數目和傳送至報表套裝的流量量而大不相同。 不過，平均而言，一行資料約為 500B (壓縮) 或 2KB (解壓縮)。將此值乘以伺服器呼叫數，可粗略估計資料饋送檔案的大小。 在您的組織開始接收資料饋送檔案後，您就可以透過將資料中的列數除以檔案總大小，來找 `hit_data.tsv` 到更精確的數字。

---
description: 本節說明資料摘要傳送中所含的檔案。
keywords: 資料摘要;工作;內容;文件;查詢;點擊資料;交付內容
subtopic: data feeds
title: 資料摘要內容 - 概觀
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 43e483f157f1c2527f671eb43a165db86c77a7ce
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 77%

---

# 資料摘要內容 — 概觀

以下小節說明如何存取和瞭解資料摘要傳送中的檔案。

## 存取資料摘要內容

若要存取資料摘要的內容：

1. 登入資料摘要目的地網站。

   這是您在建立資料摘要時設定的目的地網站，例如Amazon S3或Google Cloud Platform貯體。

1. 將壓縮的資料摘要檔案下載到您的本機電腦。

1. 使用可支援 `.tar.gz` 副檔名的程式來解壓縮壓縮檔案。

1. 按您的偏好在試算表或資料庫應用程式中開啟 `hit_data.tsv` 檔案，以便查看當天的原始資料。-->

## 資訊清單檔案 {#feed-manifest}

資訊清單檔案包含上傳資料集內每個檔案的下列詳細資料：

* 檔案名稱
* 檔案大小
* MD5 雜湊
* 檔案中包含的記錄數

資訊清單檔案的格式與 Java JAR 資訊清單檔案相同。

資訊清單檔案一律在最後以單獨的 `.txt` 檔案傳送，因此如有此檔案即代表已傳送該請求期間的完整資料集。資訊清單檔案的命名方式如下：

```text
[rsid]_[YYYY-mm-dd].txt
```

典型的資訊清單檔案包含類似下列的資料：

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

每個資訊清單檔案包含標題，指出查閱檔案總數、資料檔案以及所有資料檔案中的記錄總數。此標題之後有多個區段，包含資料摘要傳送中每個檔案的相關資訊。

有些摘要的設定為接收 `.fin` 檔案，而非 `.txt` 資訊清單。`.fin` 可指出上傳是否已完成，但不包含上傳的相關中繼資料。

## 查閱檔案

有些資料摘要欄會輸出對應到實際值的數字。查閱檔案是用來找出資料摘要欄中的數字，並將其比對實際值。例如，`browser` 點擊資料欄中的值為「497」，表示如果您檢視 `browser.tsv`，點擊來自「Microsoft Internet Explorer 8」。

請注意，`column_headers.tsv` 和 `event_list.tsv` 是資料摘要和報告套裝專屬檔案。`browser.tsv` 等其他檔案則是一般檔案。

查閱檔案會以壓縮的 zip 檔案一起傳送，命名方式如下：

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`**：包含欄標題的單一列 `hit_data.tsv`.
* **`browser.tsv`**：對應瀏覽器ID (對應至 `browser` 的易記名稱。
* **`browser_type.tsv`**：對應瀏覽器ID (對應至 `browser` 欄中選取的字元（例如「摘要」欄）。
* **`color_depth.tsv`**：對應色彩深度ID (對應至 `color` 欄的顏色深度。
* **`connection_type.tsv`**：對應連線型別ID (對應至 `connection_type` 的欄位建立連線型別。
* **`country.tsv`**：對應國家/地區ID (對應至 `country` 摘要欄)至國家名稱。
* **`javascript_version.tsv`**：對應JavaScript版本ID ( `javascript` 摘要欄)重新命名為。
* **`languages.tsv`**：對應語言ID ( `language` 摘要欄)轉換為語言。
* **`operating_systems.tsv`**：對應作業系統ID ( `os` 的欄位中輸入)，以取得作業系統名稱。
* **`plugins.tsv`**：對應外掛程式ID ( `plugin` 欄中指定欄的字元（例如「摘要」欄中的字元）。
* **`resolution.tsv`**：對應解析度ID ( `resolution` 進位欄)，以取得監視器解析度。
* **`referrer_type.tsv`**：對應反向連結型別ID (對應至反向連結 `ref_type` 」欄中)重新命名為「反向連結」。
* **`search_engines.tsv`**：對應搜尋引擎ID ( `search_engine` 欄中指定搜尋引擎名稱。
* **`event.tsv`**：對應每個事件ID (對應至 `event_list` 欄)的欄位中選取其個別事件名稱。

## 點擊資料檔案

點擊資料以 `hit_data.tsv` 檔案提供。此檔案中的資料量由傳送格式決定 (每小時或每日、單一檔案或多個檔案)。此檔案僅包含點擊資料。欄標題則與查閱檔案一同傳送。此檔案的每一行包含單一伺服器呼叫。

Adobe 傳送的檔案不一，取決於您設定的資料摘要類型而定。所有檔案都使用 ISO-8859-1 編碼。

* `[rsid]` 是指資料摘要所在的報告套裝 ID。
* `[index]` 僅用於多個檔案摘要，且是指已編頁檔案的正確順序。
* `[YYYY-mm-dd]` 指資料摘要的開始日期。
* `[HHMMSS]` 僅用於每小時摘要，且是指資料摘要的開始小時。
* `[compression_suffix]` 是指使用的壓縮類型。通常資料摘要會壓縮成 `tar.gz` 或 `zip` 檔案。

### 每日、單一檔案

收集一天的資料後，您會收到單一壓縮資料檔案和資訊清單檔案。資料檔案的名稱為：

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

擷取之後，資料檔案會包含單一 `hit_data.tsv` 檔案 (其中包含當天的所有資料)，以及任何必要欄的查閱檔案。

### 每日、多個檔案

收集一天的資料後，您會收到一或多個壓縮資料檔案和資訊清單檔案。資料檔案的名稱為：

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

擷取後，每個資料檔案都包含單一 `hit_data.tsv` (內含約 2GB 解壓縮資料)，以及任何必要欄的查閱檔案。

### 每小時、單一檔案

收集一小時的資料後，您會收到單一壓縮資料檔案和資訊清單檔案。資料檔案的名稱為：

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

擷取後，資料檔案會包含單一 `hit_data.tsv` 檔案 (其中包含該小時的所有資料)，以及任何必要欄的查閱檔案。

### 每小時、多個檔案

收集一小時的資料後，您會收到一或多個壓縮資料檔案和資訊清單檔案。資料檔案的名稱為：

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

擷取後，每個資料檔案都包含單一 `hit_data.tsv` (內含約 2GB 解壓縮資料)，以及任何必要欄的查閱檔案。

## 資料檔案大小

點擊資料檔案大小不一，主要取決於目前使用的變數數目以及傳送到報告套裝的流量總量。不過，平均而言，一行資料約為 500B (壓縮) 或 2KB (解壓縮)。將此值乘以伺服器呼叫數目，可提供資料摘要檔案的大小粗估。您的組織開始接收資料摘要檔案後，您就可以將 `hit_data.tsv` 中的列數除以檔案總大小，來找到更精確的數字。
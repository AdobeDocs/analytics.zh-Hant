---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackDownLoadLinks

若您要在網站上追蹤可下載檔案的連結，請將 設為 'true'。

If  is 'true,'  is used to determine which links are downloadable files.*`trackDownloadLinks`**`linkDownloadFileTypes`*

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

若您網站上的可下載檔案沒有連結，或是您不想要追蹤可下載檔案的點按次數，則只能將 *`trackDownloadLinks`* 變數設為 'false'。If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. 隨下載連結傳送的資料包括連結下載 URL，以及該連結的訪客點按對映資料。若 *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

## 語法和可能的值

*`trackDownloadLinks`變數應為 'true' 或 'false'。*

## 範例

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## 組態設定

無

## 缺陷、問題和提示

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.

* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.
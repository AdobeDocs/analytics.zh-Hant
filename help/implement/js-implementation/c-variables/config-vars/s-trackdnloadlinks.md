---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackDownLoadLinks

若您要在網站上追蹤可下載檔案的連結，請將 設為 'true'。

若 *`trackDownloadLinks`* 為「true」，*`linkDownloadFileTypes`* 可用來判斷哪些連結是可下載的檔案。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

若您網站上的可下載檔案沒有連結，或是您不想要追蹤可下載檔案的點按次數，則只能將 *`trackDownloadLinks`* 變數設為 'false'。若 *`trackDownloadLinks`* 為「true」，當有人點按檔案下載連結時，資料將會立即傳送至 [!DNL Analytics]。隨下載連結傳送的資料包括連結下載 URL，以及該連結的訪客點按對映資料。若&#x200B;*`trackDownloadLinks`* 為「false」，則網站上可下載檔案的連結可能會出現訪客點按對映資料報告不充分的情形。

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

* 當 *`trackDownloadLinks`* 為「false」時，訪客在您的網站上用來下載檔案的連結可能會出現訪客點按對映報告不充分的情形。

* 當 *`trackDownloadLinks`* 為「true」時，將會在訪客每次點按檔案下載連結時傳送資料。

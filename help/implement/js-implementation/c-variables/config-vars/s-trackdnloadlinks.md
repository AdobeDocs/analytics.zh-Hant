---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

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

## 退出連結和檔案下載的自動追蹤

可將 JavaScript 檔案組態為基於那些定義檔案下載類型和退出連結的參數來自動追蹤檔案下載及退出連結。

能控制自動追蹤的參數如下:

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

參數 `trackDownloadLinks` and `trackExternalLinks` determine if automatic file download and exit link tracking are enabled. 啟用後，任何檔案類型符合中其中一個值的連結都會 `linkDownloadFileTypes` 自動被追蹤為檔案下載。 任何URL中不含其中一個值的連結，都會自 `linkInternalFilters` 動視為退出連結進行追蹤。

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

### 範例 1

檔案類型 `.jpg` 和未 `.aspx` 包含在上方，因此 `linkDownloadFileTypes` 不會自動追蹤並報告為檔案下載。

The parameter `linkLeaveQueryString` modifies the logic used to determine exit links. When `linkLeaveQueryString`=false, exit links are determined using only the domain, path, and file portion of the link URL. When `linkLeaveQueryString`=true, the query string portion of the link URL is also used to determine an exit link.

### 範例 2

透過下列設定，下面的範例將被計為一個退出連結:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### 範例 3

使用下列設定時，下列連結將不會計為退出連結: 

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*注意: 單一連結只能被視為檔案下載或退出連結受到追蹤，兩者皆成立時，會優先將其視為檔案下載。如果連結是根據參數和的退出連結和檔案下載，`linkDownloadFileTypes``linkInternalFilters`則會追蹤並報告為檔案下載，而非退出連結。*
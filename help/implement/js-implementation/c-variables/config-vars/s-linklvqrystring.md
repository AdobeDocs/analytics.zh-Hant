---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkLeaveQueryString

預設情況下，查詢字串被排除在所有 報表之外。

對於部分退出連結和下載連結，URL 的重要部分可能就在查詢字串中，如下列範例 URL 所示。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

下載檔案名稱可定義在查詢字串中，因此，必須透過查詢字串使[!UICONTROL 「檔案下載」]報表更為精準。

此 *`linkLeaveQueryString`* 變數可決定是否應將查詢字串納入[!UICONTROL 「退出連結」]和[!UICONTROL 「檔案下載」]報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | 不適用 | 退出連結檔案下載 | false |

*注意：設定`linkLeaveQueryString=true`包含所有退出連結和下載連結的所有查詢字串參數。*

## 語法

```js
s.linkLeaveQueryString=[false/true]
```

## 範例

```js
s.linkLeaveQueryString=false
```

## 可能的值

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## 組態設定

此變數不需進行設定。

## 缺陷、問題和提示

* 設為 `s.linkLeaveQueryString=true` 會納入所有退出連結和下載連結的所有查詢字串參數。
* `linkLeaveQueryString` 變數不會對記錄的頁面 URL、訪客點按對映或[!UICONTROL 路徑]報表造成影響。

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
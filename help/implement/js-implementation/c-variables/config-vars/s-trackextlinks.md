---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackExternalLinks

若 為「true」，則會使用 和 來判斷所點按的任何連結是否為退出連結。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

若您網站上的可下載檔案沒有連結，或是您不想要追蹤可下載檔案的點按次數，則只能將  *`trackExternalLinks`* 變數設為 'false'。退出連結是指將訪客帶離您網站的任何連結。若&#x200B;*`trackExternalLinks`*&#x200B;為「true」，則在您點按退出連結時，將會立即傳送追蹤資料。隨退出連結傳送的資料包括連結 URL、連結名稱和該連結的訪客點按對映資料。若&#x200B;*`trackExternalLinks`* 為「false」，則網站上的退出連結可能會出現訪客點按對映資料報告不充分的情形。

## 語法和可能的值

*`trackExternalLinks`變數應為 'true' 或 'false'。*

```
js
s.trackExternalLinks=true|false
```

## 範例

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## 組態設定

無

## 缺陷、問題和提示

* 當 *`trackExternalLinks`* 為「false」時，將訪客帶離您的網站的連結可能會出現訪客點按對映報告不充分的情形。

* 當 *`trackExternalLinks`* 為「true」時，將會在訪客每次點按退出連結時 (在連結目標載入之前) 傳送資料。

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

參數`trackDownloadLinks` 和 `trackExternalLinks` 用於判斷自動檔案下載和退出連結追蹤是否已啟用。如已啟用，任何連結中的檔案類型若符合 `linkDownloadFileTypes` 中的任一個值，系統就會將該連結視為檔案下載自動加以追蹤。任何連結中的 URL 若不含 `linkInternalFilters` 中的任一個值，系統就會將該連結視為退出連結自動加以追蹤。

在 JavaScript H.25.4 (於 2013 年 2 月發行)，自動退出連結追蹤已有所更新，一律會忽略以 `#`、`about:` 或 `javascript:` 開頭的 `HREF` 屬性連結。

### 範例 1

檔案類型 `.jpg` 和 `.aspx` 未包含在上方的 `linkDownloadFileTypes`，因此系統不會自動追蹤這些類型的點擊並在報表中計為檔案下載。

參數 `linkLeaveQueryString` 會修改用以判斷退出連結的邏輯。如果 `linkLeaveQueryString`=false，系統僅會使用連結 URL 的網域、路徑及檔案來判斷退出連結。如果 `linkLeaveQueryString`=true，系統才會加碼使用連結 URL 的查詢字串來判斷退出連結。

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

*注意: 單一連結只能被視為檔案下載或退出連結受到追蹤，兩者皆成立時，會優先將其視為檔案下載。如果連結同時以參數`linkDownloadFileTypes`和`linkInternalFilters`的退出連結和檔案下載為依據，系統就會追蹤連結，並在報表中計為檔案下載，而非退出連結。*
---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

 變數是以逗號分隔的副檔名清單。

若您的網站包含檔案的連結，且檔案具有其中任何副檔名，這些連結的 URL 將出現在[!UICONTROL 「檔案下載」]報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | 不適用 | 流量 &gt; 網站流量 &gt; 檔案下載 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

此&#x200B;*`linkDownloadFileTypes`* 變數只有在 *`trackDownloadLinks`* 設為「True」時才具有相關性。

以滑鼠左鍵點按連結時，才會計入[!UICONTROL 「檔案下載」]報表中。任何在頁面載入時自動啟動的檔案下載，或是只會在重新導向後執行的檔案下載，都不會計入[!UICONTROL 「檔案下載」]報表中。當您以滑鼠右鍵按一下檔案，然後選取「另存目標...」選項時，並不會計入[!UICONTROL 「檔案下載」]報表中。

此&#x200B;*`linkDownloadFileTypes`* 變數可用來追蹤 RSS 饋送的點按次數。如果您有具有 .xml 或其他副檔名的 RSS 饋送連結，將「.xml」附加至 *`linkDownloadFileTypes`* 清單可讓您查看各個 RSS 連結的點按頻率。

## 語法和可能的值

僅包含副檔名 (無空格)。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

任何副檔名皆可包含在清單內。請留意勿將常見副檔名 (例如 htm 或 aspx) 納入   *`linkDownloadFileTypes`*。此舉將導致每次點按時都會發送額外的影像要求，而計為主要伺服器呼叫的費用。

## 範例

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## 組態設定*

無

## 缺陷、問題和提示

* 以左鍵點按下載檔案時，才會使 URL 出現在[!UICONTROL 「檔案下載」]報表中。
* 將常見副檔名納入&#x200B;*`linkDownloadFileTypes`*&#x200B;中，可能會大幅增加傳送至 Adobe 伺服器的伺服器呼叫總數。
* 伺服器端重新導向的連結或自動開始下載檔案的 HTML 頁面不會被計入，除非該副檔名位於 *`linkDownloadFileTypes`*.
* 使用 JavaScript 的連結 (如 javascript:openLink( )) 不會計入檔案下載中。

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
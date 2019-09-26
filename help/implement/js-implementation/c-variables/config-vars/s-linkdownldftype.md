---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkDownloadFileTypes

 變數是以逗號分隔的副檔名清單。

若您的網站包含檔案的連結，且檔案具有其中任何副檔名，這些連結的 URL 將出現在[!UICONTROL 「檔案下載」]報表中。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | 不適用 | 流量 &gt; 網站流量 &gt; 檔案下載 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

此 變 *`linkDownloadFileTypes`* 數僅在設為' *`trackDownloadLinks`* True'時相關。

以滑鼠左鍵點按連結時，才會計入[!UICONTROL 「檔案下載」]報表中。任何在頁面載入時自動啟動的檔案下載，或是只會在重新導向後執行的檔案下載，都不會計入[!UICONTROL 「檔案下載」]報表中。當您以滑鼠右鍵按一下檔案，然後選取「另存目標...」選項時，並不會計入[!UICONTROL 「檔案下載」]報表中。

此&#x200B;*`linkDownloadFileTypes`* 變數可用來追蹤 RSS 饋送的點按次數。如果您有RSS饋送的連結，且副檔名為。xml或其他副檔名，則在清單中附加 *`linkDownloadFileTypes`* ",xml"可讓您查看每個RSS連結的點按頻率。

## 語法和可能的值

僅包含副檔名 (無空格)。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

任何副檔名皆可包含在清單內。請留意勿將常見副檔名 (例如 htm 或 aspx) 納入 *`linkDownloadFileTypes`*。此舉將導致每次點按時都會發送額外的影像要求，而計為主要伺服器呼叫的費用。

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
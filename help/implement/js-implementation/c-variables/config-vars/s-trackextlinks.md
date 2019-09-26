---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackExternalLinks

如果為'true'，則用於判斷所點按的任何連結是否為退出連結。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

若您網站上的可下載檔案沒有連結，或是您不想要追蹤可下載檔案的點按次數，則只能將 *`trackExternalLinks`* 變數設為 'false'。退出連結是指將訪客帶離您網站的任何連結。若 *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. 隨退出連結傳送的資料包括連結 URL、連結名稱和該連結的訪客點按對映資料。若 *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

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

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.

* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.trackExternalLinks

若 為「true」，則會使用 和 來判斷所點按的任何連結是否為退出連結。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | True |

若您網站上的可下載檔案沒有連結，或是您不想要追蹤可下載檔案的點按次數，則只能將 *`trackExternalLinks`* 變數設為 'false'。退出連結是指將訪客帶離您網站的任何連結。若&#x200B;*`trackExternalLinks`*&#x200B;為「true」，則在您點按退出連結時，將會立即傳送追蹤資料。隨退出連結傳送的資料包括連結 URL、連結名稱和該連結的訪客點按對映資料。若&#x200B;*`trackExternalLinks`* 為「false」，則網站上的退出連結可能會出現訪客點按對映資料報告不充分的情形。

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

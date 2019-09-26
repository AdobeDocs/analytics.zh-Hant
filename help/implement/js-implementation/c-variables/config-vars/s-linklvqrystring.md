---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

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
| 不適用 | 不適用 | Exit Links File Downloads | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

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

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

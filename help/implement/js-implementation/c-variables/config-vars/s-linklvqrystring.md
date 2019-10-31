---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

> [!NOTE]設為 `linkLeaveQueryString=true` 會納入所有退出連結和下載連結的所有查詢字串參數。

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

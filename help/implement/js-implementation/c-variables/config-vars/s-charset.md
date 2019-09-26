---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.charSet

charSet屬性通常在JavaScript檔案中設定，Analytics會使用它將傳入資料轉換為UTF-8，以便Analytics儲存和報告。

>[!N] 注意：將資料傳送至多位元組報表套裝時，需要charSet屬性，且不應與標準報表套裝搭配使用。 使用標準 ISO 報表套裝設定 charSet 屬性可導致變數截斷或意外的字元轉換。

charSet 屬性的值應與 META 標記或 http 標題中的頁面編碼相符，即使語法稍有不同。儘管 META 標記使用別名進行編碼，charSet 的值也應使用慣用 (或官方) 名稱。

下表列出了一些更常見編碼的慣用名稱和別名。

| 慣用名稱 | 別名 |
|--- |--- |
| ISO-8859-1 | ISO_8859-1,CP819,latin1 |
| ISO-8859-2 | ISO_8859-2,latin2 |
| ISO-8859-5 | ISO_8859-5,cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Because numerous encodings and aliases exist, contact your Implementation Consultant or Adobe Customer Care to confirm the proper value for charSet if it does not appear in the table above.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

任何 charSet 參數的非空白值均可導致資料轉換為 UTF-8 儲存。所有 128-255 範圍的字元均將轉換為合適的 UTF-8 雙位元組序列並儲存。這些字元將無法在標準報表套裝中正確顯示。因此，嚴禁在標準報表套裝中使用 charSet 屬性。

同樣，charSet 參數的空白值可跳過資料轉換過程，所有 128-255 範圍中的字元均會以單位元組的形式儲存。由於這些字元的單位元組代碼均是無效的 UTF-8，這些字元將無法在多位元組報表套裝中正確顯示。因此，應始終在多位元組報表套裝中使用 charSet 參數。此外，正確值應與網頁編碼相關。

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. 但是，如果頁面上的變數包含非ASCII字元，則必 *`charSet`* 須填入變數。

## 參數

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 不適用 | CE | 不適用 | "" |

## 語法和可能的值

```js
s.charSet="character_set"
```

## 範例

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

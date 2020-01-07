---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.charSet

charSet 屬性通常設定在 JavaScript 檔案中，由 Analytics 用來將接收的資料轉換為 UTF-8 加以儲存並由 Analytics 製成報表。

>[!N注意:] 將資料傳送到多位元組報表套裝時需要使用 charSet 屬性，標準報表套裝則嚴禁使用。使用標準 ISO 報表套裝設定 charSet 屬性可導致變數截斷或意外的字元轉換。

charSet 屬性的值應與 META 標記或 http 標題中的頁面編碼相符，即使語法稍有不同。儘管 META 標記使用別名進行編碼，charSet 的值也應使用慣用 (或官方) 名稱。

下表列出了一些更常見編碼的慣用名稱和別名。

| 慣用名稱 | 別名 |
|--- |--- |
| ISO-8859-1 | ISO_8859-1,CP819,latin1 |
| ISO-8859-2 | ISO_8859-2,latin2 |
| ISO-8859-5 | ISO_8859-5,cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

由於存在大量的編碼和別名，如果 charSet 的正確值沒有出現在上面的表格中，請聯絡您的實施顧問或 Adobe 客戶服務進行確認。

如果網站中不同頁面上的網頁編碼不同，或單個 JavaScript 檔案用於多個網站，請將 JavaScript 檔案中的 charSet 屬性設定為預設值，然後依據需要重新設定每個頁面，以覆蓋預設值。例如 `s.charSet="UTF-8"` 或 `s.charSet="SJIS"`。

任何 charSet 參數的非空白值均可導致資料轉換為 UTF-8 儲存。所有 128-255 範圍的字元均將轉換為合適的 UTF-8 雙位元組序列並儲存。這些字元將無法在標準報表套裝中正確顯示。因此，嚴禁在標準報表套裝中使用 charSet 屬性。

同樣，charSet 參數的空白值可跳過資料轉換過程，所有 128-255 範圍中的字元均會以單位元組的形式儲存。由於這些字元的單位元組代碼均是無效的 UTF-8，這些字元將無法在多位元組報表套裝中正確顯示。因此，應始終在多位元組報表套裝中使用 charSet 參數。此外，正確值應與網頁編碼相關。

如果 *`charSet`* 變數包含不正確的值，則所有其他變數中的資料將會不正確地轉譯。如果您頁面上的 JavaScript 變數 (如 *`pageName`*、[!UICONTROL prop1] 或 *`channel`*) 僅包含 ASCII 字元，則無須定義 *`charSet`*。不過，如果您頁面上的變數包含非 ASCII 字元，則必須填入 *`charSet`* 變數。

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

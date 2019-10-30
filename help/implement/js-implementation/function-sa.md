---
description: s.sa() 函數可讓您在影像要求引發之前或之後，隨時動態變更頁面上的報表套裝。
keywords: Analytics 實作
seo-description: s.sa() 函數可讓您在影像要求引發之前或之後，隨時動態變更頁面上的報表套裝。
seo-title: s.sa() 函數
solution: Analytics
subtopic: 函數
title: s.sa() 函數
topic: 開發人員和實作
uuid: a6aacd10-2a5b-448b-b3b7-bed5590b71d4
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# s.sa() 函數

s.sa() 函數可讓您在影像要求引發之前或之後，隨時動態變更頁面上的報表套裝。

若您的組織要直接將資料傳送至不同的報表套裝，而不進行頁面重新載入，建議務必要使用此函數。

這項資訊適用於報告與實施皆熟稔的進階使用者。若未通盤瞭解，請勿嘗試編輯您的實施。如需進行實施變更，請與組織的客戶經理連絡。

## 函數的屬性{#section_E10CB41A0CF749F4A24C8377958E3671}

設定此函數時會使用所有先前已定義的變數，並可讓這些變數用於不同的報表套裝中。

## 實施範例 {#section_14B0B8C853244D5F82B08B995773640C}

傳送視訊資料至一個報表套裝，並傳送其餘資料至另一個報表套裝:

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

使用 s.sa() 和多套裝標記:

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```


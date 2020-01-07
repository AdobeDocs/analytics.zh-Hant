---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.linkExternalFilters

若您的網站含有許多外部網站的連結，而您不想追蹤所有的退出連結，請使用 來報告退出連結的特定子集。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 路徑 &gt; 登入與退出 &gt; 退出連結 | "" |

*`linkExternalFilters`* 變數是可與 *`linkInternalFilters`* 搭配使用的選用變數，可判斷連結是否為退出連結。退出連結被定義為將訪客帶離您網站的任何連結。無論退出連結的目標視窗是快顯視窗還是現有視窗，這都不會影響該連結是否會出現在退出連結報表中。只有在&#x200B;*`trackExternalLinks`* 設為「true」時，退出連結才會受到追蹤。*`linkExternalFilters`* 和 *`linkInternalFilters`* 中的篩選器會區分大小寫。

> [!NOTE]如果您不想要使用 *`linkExternalFilters`*，請將其刪除或設為 ""。

根據預設，*`linkExternalFilters`* 和 *`linkInternalFilters`* 中的篩選器會套用至任何連結的網域和路徑。若將 *`linkLeaveQueryString`* 設為「true」，則篩選器會套用至整個 URL (網域、路徑和查詢字串)。這些篩選器可始終被套用到 URL 的絕對路徑，即使相對路徑被用作 href 值。

有許多公司認為   *`linkInternalFilters`* 即足以供他們託管退出連結，因此不需要 *`linkExternalFilters`*。*`linkExternalFilters`* 會降低退出連結被視為外部連結的可能性。若 *`linkExternalFilters`* 具有值，則只有在連結不符合 *`linkInternalFilters`* 且不符合 *`linkExternalFilters`* 時，才會被視為外部連結。

以下範例可說明此變數的使用方式。在此範例中，頁面的 URL 為 `https://www.mysite.com/index.html`。

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

## 語法和可能的值

*`linkExternalFilters`* 變數是以逗號分隔的 ASCII 字元清單。不允許空格。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL 的任何部分皆可包含在   *`linkExternalFilters`* 中，以逗號分隔。

## 範例

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## 組態設定

無

## 缺陷、問題和提示

* *`linkExternalFilters`* 可減少您的網站上會成為退出連結的連結。請勿使用此變數取代 *`linkInternalFilters`* 來強制內部連結變成退出連結。

* 若 *`linkExternalFilters`* 應套用至某個連結的查詢字串，請確保已將 *`linkLeaveQueryString`* 設為「true」。在設為 `"true"` 之前，請參閱 [linkLeaveQueryString](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)。

* 若要停用退出連結追蹤，請將 *`trackExternalLinks`* 設為 `"false"`。

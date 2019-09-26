---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkExternalFilters

若您的網站含有許多外部網站的連結，而您不想追蹤所有的退出連結，請使用 來報告退出連結的特定子集。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 路徑 &gt; 登入與退出 &gt; 退出連結 | "" |

此  變 *`linkExternalFilters`* 數是可選變數，與 *`linkInternalFilters`* 用來判斷連結是否為退出連結。 退出連結被定義為將訪客帶離您網站的任何連結。無論退出連結的目標視窗是快顯視窗還是現有視窗，這都不會影響該連結是否會出現在退出連結報表中。只有在 *`trackExternalLinks`* is set to 'true.' 和中的篩選器 *`linkExternalFilters`* 不區分大小寫 *`linkInternalFilters`* 。

>[!NOTE]
>
>如果您不想使用，請刪 *`linkExternalFilters`*&#x200B;除它，或將它設為""。

依預設，篩選 *`linkExternalFilters`* 器清 *`linkInternalFilters`* 單會套用至任何連結的網域和路徑。 如 *`linkLeaveQueryString`* 果設為'true'，篩選器會套用至整個URL（網域、路徑和查詢字串）。 這些篩選器可始終被套用到 URL 的絕對路徑，即使相對路徑被用作 href 值。

有許多公司認為  *`linkInternalFilters`* gives them enough control over exit links that they don't need *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

以下範例可說明此變數的使用方式。In this example, the URL of the page is `https://www.mysite.com/index.html`.

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

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. 不允許空格。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL 的任何部分皆可包含在  *`linkExternalFilters`*, separated by commas.

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

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. 請勿使用此變數來取代 *`linkInternalFilters`* 強制內部連結成為退出連結。

* 如 *`linkExternalFilters`* 果應套用至連結的查詢字串，請確 *`linkLeaveQueryString`* 定設為'true'。 See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

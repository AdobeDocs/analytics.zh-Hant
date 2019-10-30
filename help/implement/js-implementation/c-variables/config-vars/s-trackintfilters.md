---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---



# s.linkInternalFilters

 變數可用來決定您網站上的哪些連結是退出連結。

這是篩選器的逗號分隔清單，它表示屬於網站組成部分的連結。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 路徑 &gt; 登入與退出 &gt; 退出連結 |  |

> [!NOTE]我們先前曾建議將 linkInternalFilters 設定為 javascript:。但是，這會導致系統將所有網域都視為外部網域，包括目前標籤所在的網域。若要將多個網域視為內部網域，您可以新增這些網域 (如下列範例所示)。

*`linkInternalFilters`* 變數可用來決定某個連結是否為退出連結；退出連結的定義為將訪客帶離您的網站的任何連結。無論退出連結的目標視窗是快顯視窗還是現有視窗，這都不會影響該連結是否會出現在退出連結報表中。只有在  *`trackExternalLinks`* 設為 `"true"` 時才會追蹤退出連結。(如需 DTM 如何處理退出連結的相關資訊，請參閱動態標籤管理文件中的[連結追蹤](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html)。)*`linkInternalFilters`* 中的篩選器不區分大小寫。

根據預設，*`linkInternalFilters`* 中的篩選器清單會套用至任何連結的網路和路徑。若將 *`linkLeaveQueryString`* 設為 `"true"`，則篩選器會套用至整個 URL (網域、路徑和查詢字串)。這些篩選器可始終被套用到 URL 的絕對路徑，即使相對路徑被用作 href 值。

請留意，您的網站的所有網域 (以及任何使用您的 JavaScript 檔案的合作夥伴)，都會納入  *`linkInternalFilters`*。若您未將所有網域納入此清單中，則位於和連結至這些網域的連結，都會被視為退出連結，而增加傳送的伺服器呼叫。如果您想要讓多個網域或公司將單一 [!DNL AppMeasurement] 用於 JavaScript 檔案，您可考慮在頁面上填入 *`linkInternalFilters`*，覆寫 JavaScript 檔案中指定的值。若您有會立即重新導向至您的主要網域的虛名網域，這些虛名網域並不需要納入清單中。

以下範例可說明此變數的使用方式。在此範例中，頁面的 URL 為 `https://www.mysite.com/index.html`。

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
...
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## 語法和可能的值

*`linkInternalFilters`* 變數是以逗號分隔的 ASCII 字元清單。不允許空格。

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## 範例

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## 組態設定

無

## 缺陷、問題和提示

* 在篩選清單中納入所有可能會提供 JavaScript 適用的 [!DNL AppMeasurement] 檔案的網域。
* 定期檢查「[!UICONTROL 路徑] &gt; [!UICONTROL 登入與退出] &gt; [!UICONTROL 退出連結]」報表，以確定該報表不含任何不正確的項目。

* 定期檢閱合作夥伴合約，以確認其中是否包含連結追蹤的相關限制。例如，合約可能禁止您追蹤出現在合作夥伴顯示廣告中的連結。將合作夥伴連結的網域新增至  *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

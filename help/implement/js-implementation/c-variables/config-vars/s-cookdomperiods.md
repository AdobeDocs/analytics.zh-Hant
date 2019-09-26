---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. 有些外掛程式也會使用此變數來判斷設定外掛程式 Cookie 所需的正確網域。

The default value for  is "2". *`cookieDomainPeriods`* This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain ,  should be "2". `www.mysite.com`*`cookieDomainPeriods`* For ,  should be "3".`www.mysite.co.jp`*`cookieDomainPeriods`*

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting  to "2" on the domain , the  and  cookies are created on the domain . *`cookieDomainPeriods`*`www.mysite.co.jp``s_cc``s_sq``co.jp`由於 `co.jp` 是無效網域，幾乎所有瀏覽器都會拒絕這些 Cookie。因此，訪客點按對映資料將會遺失，且「[!UICONTROL 訪客資料] &gt; [!UICONTROL 技術] &gt; [!UICONTROL Cookie]」報表會指出幾乎所有的訪客都拒絕 Cookie。

若&#x200B;*`cookieDomainPeriods`* 設為 "3"，但網域僅包含兩個句號，則 JavaScript 檔案會在網站的子網域上設定 Cookie。For example, if setting  to "3" on the domain , the  and  cookies are created on the domain . *`cookieDomainPeriods`*`www2.mysite.com``s_cc``s_sq``www2.mysite.com`When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example,  would still have  set to "2". `store.toys.mysite.com`*`cookieDomainPeriods`*&#x200B;此變數定義會在根網域 [!DNL mysite.com] 上正確設定 Cookie。Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | CDP | 可控制訪客 ID 的儲存與處理方式，而影響多份報表。 | "2" |

>[!NOTE]
>
>Some cloud computing services are considered Top-Level Domains, which do not allow cookies to be written. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) 如果您在這些服務上實施，且沒有設定自己的網域 (例如您正在測試自己的實施)，可能會受到 Analytics 隱私權設定影響，已封鎖所有 Cookie 的使用者會遭到移除。若發生這種情況，經系統判斷 Cookie 已停用、無作用或無法存取的所有點擊都會遭退出，因此排除在報表之外。

## 範例

手動設定變數: 

```js
s.cookieDomainPeriods = "3";
```

數個動態設定變數的範例 (若您的核心 JavaScript 檔案同時包含兩種類型):

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## 缺陷、問題和提示

* 若您發現訪客點按對映資料不存在，或「[!UICONTROL 流量] &gt; [!UICONTROL 技術] &gt; [!UICONTROL Cookie]」報表顯示有大百分比的訪客拒絕 Cookie，請檢查 *`cookieDomainPeriods`*&#x200B;的值是否正確。

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. 這可能會導致訪客在不同子網域之間切換時遺失資料。
* 此     variable was used in deprecated implementations prior to  to set the visitor ID cookie. *`cookieDomainPeriods`**`trackingServer`* Though only present in outdated code, failure to correctly define  in this circumstance puts your implementation at risk of data loss.*`cookieDomainPeriods`*
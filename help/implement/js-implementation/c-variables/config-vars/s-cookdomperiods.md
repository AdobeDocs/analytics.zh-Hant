---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomainPeriods

變數會判斷頁面 URL 網域中所含的句號數，以判定 [!DNL Analytics] Cookie `s_cc` 和 `s_sq` 設定所在的網域。有些外掛程式也會使用此變數來判斷設定外掛程式 Cookie 所需的正確網域。

*`cookieDomainPeriods`* 的預設值為「2」。若省略 *`cookieDomainPeriods`*，就會使用這個值。例如，使用網域 `www.mysite.com`，則 *`cookieDomainPeriods`* 應為「2」。針對 `www.mysite.co.jp`，*`cookieDomainPeriods`* 應為「3」。

如果將 *`cookieDomainPeriods`* 設為「2」，但網域包含三個句號，則 JavaScript 檔案會嘗試在網域尾碼上設定 Cookie。

例如，如果在網域 `www.mysite.co.jp` 上將 *`cookieDomainPeriods`* 設為「2」，則會在網域 `co.jp` 上建立 `s_cc` 和 `s_sq` Cookie。由於 `co.jp` 是無效網域，幾乎所有瀏覽器都會拒絕這些 Cookie。因此，訪客點按對映資料將會遺失，且「[!UICONTROL 訪客資料] &gt; [!UICONTROL 技術] &gt; [!UICONTROL Cookie]」報表會指出幾乎所有的訪客都拒絕 Cookie。

若&#x200B;*`cookieDomainPeriods`* 設為 "3"，但網域僅包含兩個句號，則 JavaScript 檔案會在網站的子網域上設定 Cookie。例如，如果在網域 `www2.mysite.com` 上將 *`cookieDomainPeriods`* 設為「3」，則會在網域 `www2.mysite.com` 上建立 `s_cc` 和 `s_sq` Cookie。當訪客進入您的網站的其他子網域時 (例如 `www4.mysite.com`)，所有以 `www2.mysite.com` 設定的 Cookie 都將無法讀取。

> [!NOTE] 請勿將其他子網域加入為 *`cookieDomainPeriods`* 的一部分。例如，`store.toys.mysite.com` 仍會將 *`cookieDomainPeriods`* 設為「2」。此變數定義會在根網域 [!DNL mysite.com] 上正確設定 Cookie。在此範例中將 *`cookieDomainPeriods`* 設為「3」，將會在網域 [!DNL toys.mysite.com] 上設定 Cookie，其意涵與上一個範例相同。

另請參閱 [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | CDP | 可控制訪客 ID 的儲存與處理方式，而影響多份報表。 | "2" |

>[!NOTE]
>
>將某些雲端運算服務視為頂級網域，不允許寫入 Cookie(例如 `compute.amazonaws.com`、`*.herokuapp.com`、`*.googlecode.com` 等網域)。如果您在這些服務上實施，且沒有設定自己的網域 (例如您正在測試自己的實施)，可能會受到 Analytics 隱私權設定影響，已封鎖所有 Cookie 的使用者會遭到移除。若發生這種情況，經系統判斷 Cookie 已停用、無作用或無法存取的所有點擊都會遭退出，因此排除在報表之外。

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

* 如果您發現訪客點按對映資料不存在，或[!UICONTROL 流量] &gt; [!UICONTROL 技術] &gt; [!UICONTROL Cookie] 報表顯示有很大比例的訪客拒絕 Cookie，請檢查 *`cookieDomainPeriods`* 的值是否正確無誤。

* 如果 *`cookieDomainPeriods`* 大於網域中的區段數，則會以完整網域設定 Cookie。這可能會導致訪客在不同子網域之間切換時遺失資料。
* 此    *`cookieDomainPeriods`* 變數在 *`trackingServer`* 之前的已遭取代實施中是用來設定訪客 ID Cookie。雖然僅存在於過時的程式碼中，但在此情況下，如果無法正確定義 *`cookieDomainPeriods`*，將會讓您的實施面臨資料遺失的風險。

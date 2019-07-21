---
description: ' .js 檔案可經由設定而自動選取報告套裝 ID。'
keywords: Analytics 實施
seo-description: ' .js 檔案可經由設定而自動選取報告套裝 ID。'
seo-title: 報表套裝ID-動態帳戶
solution: Analytics
title: 報表套裝ID-動態帳戶
topic: 開發人員和實施
uuid: 763a9741-309d-4795-8819-6543866047d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 報表套裝ID-動態帳戶

 .js 檔案可經由設定而自動選取報告套裝 ID。.js 檔案可根據 URL 自動傳送影像要求至報告套裝。例如，如果 URL 是 `www.mysite.com`，則會自動傳送影像要求至報告套裝 A；如果 URL 是 `www.mysite1.com`，則會自動傳送影像要求至報告套裝 B。

這些字串可能出現在下列任何位置: 

* 主機/網域 (預設設定)
* 路徑
* 查詢字串
* 主機/網域和路徑
* 路徑和查詢字串
* 完整 URL

如需將 [!DNL Analytics] 設定成自動選取[!UICONTROL 「報表套裝 ID」]的詳細資訊，請與「Adobe 現場支援」連絡。

## 定義所要比對的 URL 區段 {#section_8099162F75F641CFBE46FD814450EF36}

在下列範例 URL 中，其各個 URL 部分和所須設定的 `s.dynamicAccountMatch` 變數皆顯示於下表。(預設值是僅搜尋主機/網域名稱，會在未定義 `s.dynamicAccountMatch` 的情況下使用)。範例 URL: `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| 部分 | 範例 (請見上例) |
|---|---|
| 主機/網域名稱 | `www.client.com` |
| 路徑 | `directory1/directory2/filename.html` |
| 查詢字串 | `param1=1234&param2=4321` |
| 主機/網域和路徑 | `www.client.com/directory1/directory2/filename.html` |
| 路徑和查詢字串 | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| 部分 | `s.dynamicAccountmatch` |
| 主機/網域名稱 | 未定義 |
| 路徑 | `window.location.pathname` |
| 查詢字串 | `(window.location.search?window.location.search:"?")` |
| 主機/網域和路徑 | `window.location.host+window.location.pathname` |
| 路徑和查詢字串 | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

考量下列範例:

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## 多項規則 {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

若選取了多項規則 (請見上例)，將會由左至右執行規則。規則會在比對完成後隨即停止，如下所示 (以給定的規則集說明)。

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

The code first checks to determine if `qa.client.com` exists within the Host/Domain Name. If so, the report suite `devreportsuite1` is selected, and the match stops. 請以分號隔開多項規則。

## 預設報表套裝 {#section_0360D724929348B0B211708B5BA15647}

`s_account` 變數可先設定，並作為預設值，以防找不到指定的字串。其範例如下: 

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

In the case above, if the host/domain name did not contain either `qa.client.com` or `client.com`, the report suite *defaultreportsuiteid* would be used.

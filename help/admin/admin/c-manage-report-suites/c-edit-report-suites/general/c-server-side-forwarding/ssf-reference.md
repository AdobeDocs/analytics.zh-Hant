---
description: 伺服器端轉送呼叫之設定變數、HTTP 標題及資料訊號的完整清單和說明。
title: 伺服器端轉送資料和程式碼參考
feature: Report Suite Settings
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 97%

---

# 伺服器端轉送資料和程式碼參考

伺服器端轉送呼叫之設定變數、HTTP 標題及資料訊號的完整清單和說明。

## 設定變數 {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

前置詞為 `d_*` 的參數可識別[資料收集伺服器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=zh-Hant) (DCS) 所使用的特殊系統層級索引鍵值組。另請參閱 [DCS API 呼叫的支援屬性](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=zh-Hant)。

| 參數 | 說明 |
|--- |--- |
| `d_rs` | (透過舊版/追蹤伺服器式的伺服器端轉送完成設定) <br>設為 Analytics 收到點擊時傳入的報表套裝。 |
| `d_dst_filter` | (透過報表套裝式的伺服器端轉送完成設定) <br>設為 Analytics 收到點擊時傳入的報表套裝 ID。 |
| `d_dst` | 如果向 Analytics 發出的請求所預期的內容是有關傳回給用戶端的目的地，請設定 `d_dst=1` <br>。 |
| `d_mid` | 傳入 Analytics 的 Experience Cloud ID。 |

## HTTP 標題 {#section_0549705E76004F9585224AEF872066C0}

這些標題為包含資訊的欄位，例如 HTTP 呼叫中的資料請求和回應。

| HTTP 標題 | 說明 | Audience Manager 所接受的 h_ key |
| --- | --- | --- |
| 主機 | 這會設為在 Analytics 主機設定檔案中指定之用戶端的特定資料收集主機名稱。它會顯示為 `host name .demdex.net`。 請參閱[了解對 Demdex 網域的呼叫](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=zh-Hant)。 | `h_host` |
| User-Agent | 設為傳入 Analytics 的 User-Agent 標題。 | `h_user-agent` |
| Accept-Language | 設為傳入 Analytics 的 `Accept-Language` 標題。 | `h_accept-language` |
| Referer | 設定為傳入 Analytics 的頁面 URL 或透過傳入 Analytics 的 `Referer` 標題收集。 | `h_referer` |
| 反向連結 | 設定為傳入 Analytics 的頁面 URL 或透過傳入 Analytics 的 `Referrer` 標題收集。 | `h_referrer` |
| 日期 | 設為傳入 Analytics 的 `Date` 標題。 | `h_date` |

此外，將會從傳送要求給 DCS 的主機 IP 產生 `h_ip` 訊號。

## 客戶定義的訊號 {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

前置詞為 `c_` 的參數可識別客戶定義的變數。另請參閱 [DCS API 呼叫的支援屬性](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=zh-Hant)。

| 訊號 | 說明 |
| --- |--- |
| `c_browserWidth` 與 `c_browserHeight` | 瀏覽器視窗寬度和高度。 |
| `c_campaign` | 由 `s.campaign` 所設定。 |
| `c_channel` | 由 `s.channel` 所設定。 |
| `c_clientDateTime` | 時間戳記格式為 `dd/mm/yyy hh:mm:ss  W TZ`。 `TZ` 的單位為分鐘，且符合 `Date.getTimezoneOffset` 方法的傳回。 |
| `c_colorDepth` | 指定為 16 或 32 位元色彩。 |
| `c_connectionType` | 指定連線類型。選項包括：<ul><li>數據機</li><li>LAN</li></ul> |
| `c_contextData.*` | 範例：<ul><li>AppMeasurement：`s.contextData`</li><li>[&quot;category&quot;] = &quot;news&quot;;</li><li>訊號：`c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | 指定 Cookie 是否可啟用。選項包括：是、否、未知 |
| `c_currencyCode` | 用於交易的貨幣類型。 |
| `c_evar#` | 自訂 eVar |
| `c_events` | 由 `s.events` 所設定。 |
| `c_hier#` | 自訂階層變數。 |
| `c_javaEnabled` | 指定 Java 是否可啟用。選項包括：是、否、未知 |
| `c_javaScriptVersion` | 瀏覽器支援的 JavaScript 版本。 |
| `c_latitude` | 緯度數值 |
| `c_linkClick` | 選項包括：自訂、下載退出 |
| `c_linkCustomName` | 為連結提供的自訂名稱 (如果有的話)。 |
| `c_linkDownloadURL` | 下載連結的 URL。 |
| `c_linkExitURL` | 退出連結 URL。 |
| `c_list#` | 自訂清單變數。 |
| `c_longitude` | 經度數值。 |
| `c_mediaPlayerType` | 適用於媒體串流追蹤請求。選項包括：其他、primetime |
| `c_pageName` | 頁面名稱 (如果有設定)。 |
| `c_pageURL` | 瀏覽器網址列中的頁面位址。 |
| `c_products` | 產品字串 (由 `s.products` 所設定)。 |
| `c_prop` | 自訂 Prop。 |
| `c_purchaseID` | 購買的唯一 ID。 |
| `c_referrer` | 目前頁面之前的頁面。 |
| `c_screenResolution` | 螢幕寬度和高度 (以像素計)。 |
| `c_server` | 網頁伺服器名稱 (由 `s.server` 所設定)。 |
| `c_state` | 地理區域 (由 `s.state` 所設定)。 |
| `c_timezone` | 時間差 (以小時計)。 |
| `c_transactionID` | 交易的唯一 ID。 |
| `c_zip` | 郵遞區號 (由 `s.zip` 所設定)。 |

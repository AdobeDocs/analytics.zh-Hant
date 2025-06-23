---
title: 資料彙集查詢參數
description: 列出影像要求中使用的所有查詢字串參數。
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 100%

---

# 資料彙集查詢參數

下表列出 Adobe 在影像要求中使用的所有查詢字串參數。在使用[封包分析器](packet-monitor.md)進行除錯時、[對影像要求進行硬式編碼](../other/hardcoded.md)時，或使用[動態變數](../vars/page-vars/dynamic-variables.md)時，都可使用此資訊。

| 參數 | Analytics 實施變數 | 說明 |
| --- | --- | --- |
| `aamlh` | 無 | Audience Manager 位置提示：用於 Experience Cloud 共用輪廓整合。 |
| `aamb` | 無 | Audience Manager Blob：用於 Experience Cloud 共用輪廓整合。 |
| `aid` | 無 | Analytics 訪客 ID。 |
| `AQB` | 無 | 指出影像要求查詢字串的開頭。 |
| `AQE` | 無 | 指出影像要求的結尾，表示要求並未被截斷。 |
| `bh` | 無 | 瀏覽器高度 (像素)。用於[瀏覽器高度](/help/components/dimensions/browser-height.md)維度。 |
| `bw` | 無 | 瀏覽器寬度 (像素)。用於[瀏覽器寬度](/help/components/dimensions/browser-width.md)維度。 |
| `c` | 無 | 色彩品質 (位元)用於[色彩深度](/help/components/dimensions/color-depth.md)維度。 |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | 指出上下文資料變數的開頭。絕不包含值。 |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | 指出上下文資料變數的結尾。絕不包含值。 |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Prop](/help/components/dimensions/prop.md) (或自訂流量變數)。 |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | 點擊中使用的貨幣類型。 |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | 網域中的句點數。用於協助正確儲存 Cookie。 |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | 影像要求的字元編碼。 |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | 訪客 Cookie 的期限。 |
| `ch` | [`channel`](../vars/page-vars/channel.md) | 用於[網站區段](/help/components/dimensions/site-section.md)維度。 |
| `cp` | 無 | 用於[點擊類型](/help/components/dimensions/hit-type.md)維度。 |
| `ct` | 無 | 用於[連線類型](/help/components/dimensions/connection-type.md)維度。 |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | 表示動態變數的用途。 |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | `events` 查詢字串的簡稱。 |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | 頁面上事件的逗號分隔清單。供大部分的[量度](/help/components/metrics/overview.md)使用。 |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | 頁面目前的 URL，最多 255 個位元組。用於[頁面 URL](/help/components/dimensions/page-url.md) 維度。 |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | 系統會分割長度超過 255 個位元組的 URL。前 255 個位元組會出現在 `g` 參數中，其餘的所有位元組則會出現在 `-g` 參數中。 |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | `pageName` 查詢字串的簡稱。 |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | `pageType` 查詢字串的簡稱。 |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | 表示 [用戶端提示](/help/technotes/client-hints.md) 的幾個變數的前置詞。 |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | 階層維度。 |
| `hp` | 無 | 已不再使用。在舊版 Adobe Analytics 中，會判斷目前的 URL 是否為瀏覽器首頁。 |
| `j` | 無 | 瀏覽器中安裝的 JavaScript 版本。 |
| `k` | 無 | 用於 [Cookie 支援](/help/components/dimensions/cookie-support.md)維度。 |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | 清單變數。 |
| `lrt` | 無 | 「上次請求時間」，即上次請求的往返時間，以毫秒為單位。只有在從一個頁面傳送多個請求或者頁面是單頁應用程式 (SPA) 時，才會傳送它。 |
| `mid` | 無 | Experience Cloud 訪客 ID。 |
| `ndh` | 無 | 指出影像要求是否源自 AppMeasurement 的標幟。 |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | 協助判斷設定 Cookie 的位置。 |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | 最後一頁的物件識別碼。用於 Activity Map。 |
| `ot` | 無 | 最後一頁的物件名稱。用於舊版 Activity Map。 |
| `p` | 無 | 已不再使用。瀏覽器中使用的外掛程式清單。 |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | 用於[頁面](/help/components/dimensions/page.md)維度。 |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | 用於[找不到頁面](/help/components/dimensions/pages-not-found.md)維度。 |
| `pccr` | 無 | 僅為新訪客設定，且一律設為 `true`。如果訪客拒絕 Cookie，則可防止無限重新導向。 |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | 判斷自訂連結的類型。[自訂連結](/help/components/dimensions/custom-link.md)、[下載連結](/help/components/dimensions/download-link.md)和[退出連結](/help/components/dimensions/exit-link.md)的必要項目。 |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | 發生自訂連結的 URL。 |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | 自訂連結友好名稱。 |
| `pev3` | 無 | 已不再使用。追蹤舊版視訊報表中的里程碑。 |
| `pf` | 無 | 平台標幟；僅供 Adobe 使用。不可變更。 |
| `pid` | 無 | 最後一頁的頁面識別碼。用於舊版 Activity Map。 |
| `pidt` | 無 | 最後一頁的頁面識別碼類型。用於舊版 Activity Map。 |
| `pl` | [`products`](../vars/page-vars/products.md) | `products` 查詢字串的簡稱。 |
| `products` | [`products`](../vars/page-vars/products.md) | 產品變數。用於[產品](/help/components/dimensions/product.md)和[類別](/help/components/dimensions/category.md)維度。 |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | 用於移除重複購買項目。 |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | 點擊的反向連結 URL。用於流量來源維度，例如[反向連結](/help/components/dimensions/referrer.md)和[反向連結網域](/help/components/dimensions/referring-domain.md) |
| `s` | 無 | 螢幕解析度，單位為 `width x height`。用於[螢幕解析度](/help/components/dimensions/monitor-resolution.md)維度。 |
| `server` | [`server`](../vars/page-vars/server.md) | [「伺服器」維度。](/help/components/dimensions/server.md) |
| `sv` | [`server`](../vars/page-vars/server.md) | `server` 查詢字串的簡稱。 |
| `state` | [`state`](../vars/page-vars/state.md) | 「狀態」維度。 |
| `t` | 無 | 產生點擊的日期/時間。使用 `dd/mm/yyyy hh:mm:ss w o` 格式。<br>- `dd/mm/yyyy hh:mm:ss` 是 JavaScript 的日期/時間格式。`0` 月為一月，`11` 月是十二月。<br>- `w` 是一週中的某天。`0` 是週日，而 `6` 是週六。<br>- `o` 是以分鐘為單位的負 GMT 時差。例如，`420` 是 GMT-7。 |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | 隨點擊設定的自訂時間戳記。通常用於離線追蹤。 |
| `v` | 無 | 用於 [Java 已啟用](/help/components/dimensions/java-enabled.md)維度。 |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [「追蹤代碼」維度。](/help/components/dimensions/tracking-code.md) |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md) (或自訂轉換維度)。 |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | 訪客 ID 變數。 |
| `vidn` | 無 | 由 AppMeasurement 為新訪客設定。包含儲存在訪客 Cookie 中的 ID 值。 |
| `vmk` | `vmk` | 已不再使用。訪客移轉金鑰，有助於將實施從第三方移轉至第一方 Cookie。 |
| `vvp` | `variableProvider` | 用於 Data Connectors。 |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | 與 Data Sources 搭配使用，將線上和離線資料繫結在一起。 |
| `zip` | [`zip`](../vars/page-vars/zip.md) | 用於[郵遞區號](/help/components/dimensions/zip-code.md)維度。 |

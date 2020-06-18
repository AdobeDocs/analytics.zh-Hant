---
title: 資料彙集查詢參數
description: 列出影像要求中使用的所有查詢字串參數。
translation-type: tm+mt
source-git-commit: edf3ac3ebc99444b86bcd9239cef9ed84d797565
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 75%

---


# 資料彙集查詢參數

下表列出 Adobe 在影像要求中使用的所有查詢字串參數。在使用[封包分析器](packet-monitor.md)進行除錯時、[對影像要求進行硬式編碼](../other/hardcoded.md)時，或使用[動態變數](../vars/page-vars/dynamic-variables.md)時，都可使用此資訊。

| 參數 | Analytics 實施變數 | 說明 |
| --- | --- | --- |
| `aamlh` | 無 | Audience Manager 位置提示：用於 Experience Cloud 共用設定檔整合。 |
| `aamb` | 無 | Audience Manager Blob：用於 Experience Cloud 共用設定檔整合。 |
| `aid` | 無 | Analytics 訪客 ID。 |
| `AQB` | 無 | 指出影像要求查詢字串的開頭。 |
| `AQE` | 無 | 指出影像要求的結尾，表示要求並未被截斷。 |
| `bh` | 無 | 瀏覽器高度 (像素)。Used in the [Browser height](/help/components/dimensions/browser-height.md) dimension. |
| `bw` | 無 | 瀏覽器寬度 (像素)。Used in the [Browser width](/help/components/dimensions/browser-width.md) dimension. |
| `c` | 無 | 色彩品質 (位元)Used in the [Color depth](/help/components/dimensions/color-depth.md) dimension. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | 指出上下文資料變數的開頭。絕不包含值。 |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | 指出上下文資料變數的結尾。絕不包含值。 |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Prop](/help/components/dimensions/prop.md)，或自訂流量變數。 |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | 點擊中使用的貨幣類型。 |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | 網域中的句點數。用於協助正確儲存 Cookie。 |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | 影像要求的字元編碼。 |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | 訪客 Cookie 的期限。 |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Used in the [Site sections](/help/components/dimensions/site-section.md) dimension. |
| `cp` | 無 | Used in the [Hit Type](/help/components/dimensions/hit-type.md) dimension. |
| `ct` | 無 | Used in the [Connection Type](/help/components/dimensions/connection-type.md) dimension. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | 表示動態變數的用途。 |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | `events` 查詢字串的簡稱。 |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | 頁面上事件的逗號分隔清單。大部分量度 [使用](/help/components/metrics/overview.md)。 |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | 頁面的目前URL，最多255個位元組。 Used in the [Page URL](/help/components/dimensions/page-url.md) dimension. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | 系統會分割長度超過 255 個位元組的 URL。前 255 個位元組會出現在 `g` 參數中，其餘的所有位元組則會出現在 `-g` 參數中。 |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | `pageName` 查詢字串的簡稱。 |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | `pageType` 查詢字串的簡稱。 |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | 階層維度。 |
| `hp` | 無 | 已不再使用。在舊版 Adobe Analytics 中，會判斷目前的 URL 是否為瀏覽器首頁。 |
| `j` | 無 | 瀏覽器中安裝的 JavaScript 版本。 |
| `k` | 無 | Used in the [Cookie support](/help/components/dimensions/cookie-support.md) dimension. |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | 清單變數。 |
| `mid` | 無 | Experience Cloud 訪客 ID。 |
| `ndh` | 無 | 指出影像要求是否源自 AppMeasurement 的標幟。 |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | 協助判斷設定 Cookie 的位置。 |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | 最後一頁的物件識別碼。用於 Activity Map。 |
| `ot` | 無 | 最後一頁的物件名稱。用於舊版 Activity Map。 |
| `p` | 無 | 已不再使用。瀏覽器中使用的外掛程式清單。 |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Used in the [Page](/help/components/dimensions/page.md) dimension. |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Used in the [Pages not found](/help/components/dimensions/pages-not-found.md) dimension. |
| `pccr` | 無 | 僅為新訪客設定，且一律設為 `true`。協助防止無限重導。 |
| `pe` | [`linkType`](../vars/config-vars/linktype.md) | 判斷自訂連結的類型。自訂連 [結、下載連結](/help/components/dimensions/custom-link.md)[，以及退出連](/help/components/dimensions/download-link.md)結需要 [](/help/components/dimensions/exit-link.md)。 |
| `pev1` | 無 | 發生自訂連結的 URL。 |
| `pev2` | [`linkName`](../vars/config-vars/linkname.md) | 自訂連結友好名稱。 |
| `pev3` | 無 | 已不再使用。追蹤舊版視訊報表中的里程碑。 |
| `pf` | 無 | 平台標幟；僅供 Adobe 使用。不可變更。 |
| `pid` | 無 | 最後一頁的頁面識別碼。用於舊版 Activity Map。 |
| `pidt` | 無 | 最後一頁的頁面識別碼類型。用於舊版 Activity Map。 |
| `pl` | [`products`](../vars/page-vars/products.md) | `products` 查詢字串的簡稱。 |
| `products` | [`products`](../vars/page-vars/products.md) | 產品變數。用於「產 [品](/help/components/dimensions/product.md) 」和「 [類別](/help/components/dimensions/category.md) 」維。 |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | 用於移除重複購買項目。 |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | 點擊的反向連結 URL。用於流量來源維度，例如反向連 [結](/help/components/dimensions/referrer.md) 和反 [向連結網域](/help/components/dimensions/referring-domain.md) |
| `s` | 無 | 螢幕解析度，單位為 `width x height`。Used in the [Monitor resolutions](/help/components/dimensions/monitor-resolution.md) dimension. |
| `server` | [`server`](../vars/page-vars/server.md) | [「伺服器」維度。](/help/components/dimensions/server.md) |
| `sv` | [`server`](../vars/page-vars/server.md) | `server` 查詢字串的簡稱。 |
| `state` | [`state`](../vars/page-vars/state.md) | 「狀態」維度。 |
| `t` | 無 | 產生點擊的日期/時間。使用 `dd/mm/yyyy hh:mm:ss w o` 格式。<br>- `dd/mm/yyyy hh:mm:ss` 是 JavaScript 的日期/時間格式。`0` 月為一月，`11` 月是十二月。<br>- `w` 是一週中的某天。`0` 是週日，而 `6` 是週六。<br>- `o` 是以分鐘為單位的負 GMT 時差。例如，`420` 是 GMT-7。 |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | 隨點擊設定的自訂時間戳記。通常用於離線追蹤。 |
| `v` | 無 | Used in the [Java enabled](/help/components/dimensions/java-enabled.md) dimension. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [「追蹤代碼」維度。](/help/components/dimensions/tracking-code.md) |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md)，或自訂轉換維度。 |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | 訪客 ID 變數。 |
| `vmk` | `vmk` | 已不再使用。訪客移轉金鑰，可協助將實作從協力廠商移轉至第一方Cookie。 |
| `vvp` | `variableProvider` | 用於 Data Connectors。 |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | 與Data Sources搭配使用，將線上和離線資料連結在一起。 |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Used in the [Zip code](/help/components/dimensions/zip-code.md) dimension. |

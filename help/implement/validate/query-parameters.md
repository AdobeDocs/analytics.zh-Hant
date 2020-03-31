---
title: 資料彙集查詢參數
description: 列出影像要求中使用的所有查詢字串參數。
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

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
| `bh` | 無 | 瀏覽器高度 (像素)。用於「瀏覽器高度」維度。 |
| `bw` | 無 | 瀏覽器寬度 (像素)。用於「瀏覽器寬度」維度。 |
| `c` | 無 | 色彩品質 (位元)用於「顏色深度」維度。 |
| `c.` | `contextData` | 指出上下文資料變數的開頭。絕不包含值。 |
| `.c` | `contextData` | 指出上下文資料變數的結尾。絕不包含值。 |
| `c1` - `c75` | `prop1` - `prop75` | 自訂流量變數。 |
| `cc` | `currencyCode` | 點擊中使用的貨幣類型。 |
| `cdp` | `cookieDomainPeriods` | 網域中的句點數。用於協助正確儲存 Cookie。 |
| `ce` | `charSet` | 影像要求的字元編碼。 |
| `cl` | `cookieLifetime` | 訪客 Cookie 的期限。 |
| `ch` | `channel` | 用於「網站區域」維度。 |
| `cp` | 無 | 用於「點擊類型」維度。 |
| `ct` | 無 | 用於「連線類型」維度。 |
| `D` | `dynamicVariablePrefix` | 表示動態變數的用途。 |
| `ev` | `events` | `events` 查詢字串的簡稱。 |
| `events` | `events` | 頁面上事件的逗號分隔清單。 |
| `g` | `pageURL` | 目前頁面的 URL，最多 255 個位元組。 |
| `-g` | `pageURL` | 系統會分割長度超過 255 個位元組的 URL。前 255 個位元組會出現在 `g` 參數中，其餘的所有位元組則會出現在 `-g` 參數中。 |
| `gn` | `pageName` | `pageName` 查詢字串的簡稱。 |
| `gt` | `pageType` | `pageType` 查詢字串的簡稱。 |
| `h1` - `h5` | `hier1` - `hier5` | 階層變數。 |
| `hp` | 無 | 已不再使用。在舊版 Adobe Analytics 中，會判斷目前的 URL 是否為瀏覽器首頁。 |
| `j` | 無 | 瀏覽器中安裝的 JavaScript 版本。 |
| `k` | 無 | 用於「Cookie 支援」維度。 |
| `l1` - `l3` | `list1` - `list3` | 清單變數。 |
| `mid` | 無 | Experience Cloud 訪客 ID。 |
| `ndh` | 無 | 指出影像要求是否源自 AppMeasurement 的標幟。 |
| `ns` | `visitorNameSpace` | 協助判斷設定 Cookie 的位置。 |
| `oid` | `objectID` | 最後一頁的物件識別碼。用於 Activity Map。 |
| `ot` | 無 | 最後一頁的物件名稱。用於舊版 Activity Map。 |
| `p` | 無 | 已不再使用。瀏覽器中使用的外掛程式清單。 |
| `pageName` | `pageName` | 用於「頁面」維度。 |
| `pageType` | `pageType` | 用於「找不到頁面」維度。 |
| `pccr` | 無 | 僅為新訪客設定，且一律設為 `true`。防止無限重新導向。 |
| `pe` | `linkType` | 判斷自訂連結的類型。 |
| `pev1` | 無 | 發生自訂連結的 URL。 |
| `pev2` | 無 | 自訂連結友好名稱。 |
| `pev3` | 無 | 已不再使用。追蹤舊版視訊報表中的里程碑。 |
| `pf` | 無 | 平台標幟；僅供 Adobe 使用。不可變更。 |
| `pid` | 無 | 最後一頁的頁面識別碼。用於舊版 Activity Map。 |
| `pidt` | 無 | 最後一頁的頁面識別碼類型。用於舊版 Activity Map。 |
| `pl` | `products` | `products` 查詢字串的簡稱。 |
| `products` | `products` | 產品變數。 |
| `purchaseID` | `purchaseID` | 用於移除重複購買項目。 |
| `r` | `referrer` | 點擊的反向連結 URL。 |
| `s` | 無 | 用於「螢幕解析度」維度。螢幕解析度，單位為 `width x height`。 |
| `server` | `server` | 「伺服器」維度。 |
| `sv` | `server` | `server` 查詢字串的簡稱。 |
| `state` | `state` | 「狀態」維度。 |
| `t` | 無 | 產生點擊的日期/時間。使用 `dd/mm/yyyy hh:mm:ss w o` 格式。<br>- `dd/mm/yyyy hh:mm:ss` 是 JavaScript 的日期/時間格式。`0` 月為一月，`11` 月是十二月。<br>- `w` 是一週中的某天。`0` 是週日，而 `6` 是週六。<br>- `o` 是以分鐘為單位的負 GMT 時差。例如，`420` 是 GMT-7。 |
| `ts` | `timestamp` | 隨點擊設定的自訂時間戳記。通常用於離線追蹤。 |
| `v` | 無 | 用於「Java 已啟用」維度。 |
| `v0` | `campaign` | 「追蹤代碼」維度。 |
| `v1` - `v250` | `evar1` - `eVar250` | 自訂轉換維度。 |
| `vid` | `visitorID` | 訪客 ID 變數。 |
| `vmk` | `vmk` | 已不再使用。協助從第三方移轉至第一方 Cookie。 |
| `vvp` | `variableProvider` | 用於 Data Connectors。 |
| `xact` | `transactionID` | 與 Data Sources 搭配使用，將資料連結在一起。 |
| `zip` | `zip` | 用於「郵遞區號」維度。 |

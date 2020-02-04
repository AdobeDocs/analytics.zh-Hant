---
title: 資料彙集查詢參數
description: 列出影像請求中使用的所有查詢字串參數。
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# 資料彙集查詢參數

下表列出Adobe在影像要求中使用的所有查詢字串參數。 在使用封包分析器進行除錯時 [、硬式編碼](packet-monitor.md)影像要求時 [，或使用動態變數時，都可使](../other/hardcoded.md)用這項資訊 [](../vars/page-vars/dynamic-variables.md)。

| 參數 | Analytics實作變數 | 說明 |
| --- | --- | --- |
| `aamlh` | 無 | Audience manager位置提示。用於Experience cloud共用設定檔整合。 |
| `aamb` | 無 | Audience Manager Blob。用於Experience cloud共用設定檔整合。 |
| `aid` | 無 | Analytics 訪客 ID. |
| `AQB` | 無 | 指出影像請求查詢字串的開頭。 |
| `AQE` | 無 | 指出影像請求的結束，表示請求未截斷。 |
| `bh` | 無 | 瀏覽器高度（像素）。 用於「瀏覽器高度」維度。 |
| `bw` | 無 | 瀏覽器寬度（像素）。 用於「瀏覽器寬度」維度。 |
| `c` | 無 | 色彩品質（以位元為單位）。 用於「顏色深度」尺寸。 |
| `c.` | `contextData` | 指出上下文資料變數的開頭。 從不包含值。 |
| `.c` | `contextData` | 指出上下文資料變數的結尾。 從不包含值。 |
| `c1` - `c75` | `prop1` - `prop75` | 自訂流量變數. |
| `cc` | `currencyCode` | 點擊中使用的貨幣類型。 |
| `cdp` | `cookieDomainPeriods` | 網域中的句點數。 用於協助正確儲存Cookie。 |
| `ce` | `charSet` | 影像請求的字元編碼. |
| `cl` | `cookieLifetime` | 訪客 Cookie 的期限。 |
| `ch` | `channel` | 用於「網站區域」維度。 |
| `cp` | 無 | 用於「點擊類型」維度。 |
| `ct` | 無 | 用於「連接類型」維。 |
| `D` | `dynamicVariablePrefix` | 表示動態變數的用途。 |
| `ev` | `events` | 查詢字串 `events` 的速記。 |
| `events` | `events` | 頁面上事件的逗號分隔清單。 |
| `g` | `pageURL` | 目前頁面的 URL，最多 255 個位元組。 |
| `-g` | `pageURL` | 長度超過255個位元組的URL會被分割。 前255個位元組會出現在參數中， `g` 其餘的所有位元組都會出現在參數 `-g` 中。 |
| `gn` | `pageName` | 查詢字串 `pageName` 的速記。 |
| `gt` | `pageType` | 查詢字串 `pageType` 的速記。 |
| `h1` - `h5` | `hier1` - `hier5` | 階層變數. |
| `hp` | 無 | 已不再使用。在舊版Adobe Analytics中，已判斷目前的URL是否為瀏覽器首頁。 |
| `j` | 無 | 瀏覽器中安裝的JavaScript版本。 |
| `k` | 無 | 用於Cookie支援維度。 |
| `l1` - `l3` | `list1` - `list3` | 清單變數。 |
| `mid` | 無 | Experience cloud訪客ID。 |
| `ndh` | 無 | 指出影像要求是否源自AppMeasurement的旗標。 |
| `ns` | `visitorNameSpace` | 協助判斷Cookie的設定位置。 |
| `oid` | `objectID` | 最後一頁的物件識別碼。 用於Activity Map。 |
| `ot` | 無 | 最後一頁的物件名稱。 用於舊版Activity Map。 |
| `p` | 無 | 已不再使用。瀏覽器中使用的外掛程式清單。 |
| `pageName` | `pageName` | 用於頁面維度。 |
| `pageType` | `pageType` | 用於「找不到頁面」維度。 |
| `pccr` | 無 | 僅為新訪客設定，且一律設為 `true`。 防止無限重新導向。 |
| `pe` | `linkType` | 決定自訂連結的類型。 |
| `pev1` | 無 | 發生自訂連結的URL。 |
| `pev2` | 無 | 自訂連結友好名稱. |
| `pev3` | 無 | 已不再使用。追蹤視訊報表舊版中的里程碑。 |
| `pf` | 無 | 平台標誌；僅供Adobe使用。 不可變更。 |
| `pid` | 無 | 最後一頁的頁面識別碼。 用於舊版Activity Map。 |
| `pidt` | 無 | 最後一頁的頁面識別碼類型。 用於舊版Activity Map。 |
| `pl` | `products` | 查詢字串 `products` 的速記。 |
| `products` | `products` | 產品變數. |
| `purchaseID` | `purchaseID` | 用於去重複化購買。 |
| `r` | `referrer` | 點擊的反向連結URL。 |
| `s` | 無 | 用於「監視器解析度」維。 螢幕解析度，在中 `width x height`。 |
| `server` | `server` | 伺服器維。 |
| `sv` | `server` | 查詢字串 `server` 的速記。 |
| `state` | `state` | 狀態維。 |
| `t` | 無 | 產生的點擊日期／時間。 使用格式 `dd/mm/yyyy hh:mm:ss w o`。<br>- `dd/mm/yyyy hh:mm:ss` 是JavaScript中的日期／時間。 月 `0` 是一月，月 `11` 是十二月。<br>- `w` 是一週中的某天。 `0` 是週日，而 `6` 是週六。<br>- `o` 是以分鐘為單位的負GMT偏移。 例如， `420` 是GMT-7。 |
| `ts` | `timestamp` | 隨點擊設定的自訂時間戳記。 通常用於離線追蹤。 |
| `v` | 無 | 用於Java Enabled維。 |
| `v0` | `campaign` | 追蹤代碼維度。 |
| `v1` - `v250` | `evar1` - `eVar250` | 自訂轉換維度。 |
| `vid` | `visitorID` | 訪客 ID 變數。 |
| `vmk` | `vmk` | 已不再使用。已協助從協力廠商移轉至第一方Cookie。 |
| `vvp` | `variableProvider` | 用於資料連接器。 |
| `xact` | `transactionID` | 與Data Sources搭配使用，將資料連結在一起。 |
| `zip` | `zip` | 用於郵遞區號維度。 |

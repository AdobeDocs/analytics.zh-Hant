---
title: 資料彙集查詢參數
description: 列出影像要求中使用的所有查詢字串參數。
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 1079
ht-degree: 44%

---

# 資料彙集查詢參數

下表列出 Adobe 在影像要求中使用的所有查詢字串參數。 使用[封包分析器](packet-monitor.md)進行偵錯時、[硬式編碼影像要求](../other/hardcoded.md)時，或使用[動態變數](../vars/page-vars/dynamic-variables.md)時，此資訊非常有用。

| 參數 | Analytics 實施變數 | 說明 |
| --- | --- | --- |
| `aamlh` | 無 | Audience Manager位置提示。 識別透過Experience Cloud ID服務同步Audience Manager ID時所用的地區資料中心。 |
| `aamb` | 無 | Audience Manager blob. 透過Experience Cloud ID服務在ID同步期間傳遞的編碼Audience Manager設定檔資料。 |
| `aid` | 無 | 舊版Analytics訪客ID，儲存在`s_vi` Cookie中。 已由現代實作中的`mid`引數取代。 |
| `AQB` | 無 | 指出影像要求查詢字串的開頭。 |
| `AQE` | 無 | 指出影像要求的結尾，表示要求並未被截斷。 |
| `bh` | 無 | 瀏覽器高度 (像素)。 用於[[!UICONTROL 瀏覽器高度]](/help/components/dimensions/browser-height.md)維度。 |
| `bw` | 無 | 瀏覽器寬度 (像素)。 用於[[!UICONTROL 瀏覽器寬度]](/help/components/dimensions/browser-width.md)維度。 |
| `c` | 無 | 色彩品質 (位元) 用於[[!UICONTROL 色彩深度]](/help/components/dimensions/color-depth.md)維度。 |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | 指出上下文資料變數的開頭。 絕不包含值。 |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | 指出上下文資料變數的結尾。 絕不包含值。 |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Prop](/help/components/dimensions/prop.md) (或自訂流量變數)。 |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | 點擊中使用的貨幣類型。 |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **已不再使用。** 網域中的句點數。 |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | 影像要求的字元編碼。 |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | 訪客 Cookie 的期限。 |
| `ch` | [`channel`](../vars/page-vars/channel.md) | 用於[[!UICONTROL 網站區段]](/help/components/dimensions/site-section.md)維度。 |
| `cp` | [`customerPerspective`](../vars/page-vars/customerperspective.md) | 指定當應用程式於前景或背景時，是否要發生行動應用程式點選。 用於[[!UICONTROL 點選型別]](/help/components/dimensions/hit-type.md)維度。 |
| `ct` | 無 | 用於[[!UICONTROL 連線型別]](/help/components/dimensions/connection-type.md)維度。 |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | 表示動態變數的用途。 |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | `events`引數的簡稱。 |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | 頁面上事件的逗號分隔清單。 供大部分的[量度](/help/components/metrics/overview.md)使用。 |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | 頁面目前的 URL，最多 255 個位元組。 用於[[!UICONTROL 頁面 URL]](/help/components/dimensions/page-url.md) 維度。 |
| `-g` | [`pageURL`](../vars/page-vars/pageurl.md) | 系統會分割長度超過 255 個位元組的 URL。 前 255 個位元組會出現在 `g` 參數中，其餘的所有位元組則會出現在 `-g` 參數中。 |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | `pageName`引數的簡稱。 |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | `pageType`引數的簡稱。 |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | 表示 [用戶端提示](/help/technotes/client-hints.md) 的幾個變數的前置詞。 |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/page-variables.md#retired-page-variables) | **已不再使用。** 階層維度。 |
| `hp` | 無 | **已不再使用。** 在舊版 Adobe Analytics 中，會判斷目前的 URL 是否為瀏覽器首頁。 |
| `j` | 無 | **已不再使用。** 瀏覽器中安裝的 JavaScript 版本。 |
| `k` | 無 | 用於 [[!UICONTROL Cookie 支援]](/help/components/dimensions/cookie-support.md)維度。 |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | 清單變數。 |
| `lat` | 無 | **已不再使用。** 緯度。 由舊版行動SDK實作設定；目前的行動實作會透過資料串流傳送地理位置。 |
| `lon` | 無 | **已不再使用。** 經度。 由舊版行動SDK實作設定；目前的行動實作會透過資料串流傳送地理位置。 |
| `lrt` | 無 | 「上次請求時間」，即上次請求的往返時間，以毫秒為單位。 只有在從單一頁面(例如單頁應用程式(SPA))傳送多個請求時，才會傳送它。 |
| `mcorgid` | 無 | Experience Cloud組織ID，可向Experience Cloud ID服務識別組織。 |
| `mid` | 無 | 用於[[!UICONTROL Experience Cloud訪客ID]](/help/components/dimensions/experience-cloud-visitor-id.md)維度。 |
| `ms_a` | 無 | 當追蹤的串流媒體是音訊而非視訊時，Media SDK將設為`1`。 |
| `ndh` | 無 | AppMeasurement新增至其產生的每個影像請求。 由於硬式編碼請求通常會忽略它，因此它的存在表示點選來自AppMeasurement。 |
| `ns` | [`visitorNameSpace`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **已不再使用。** 協助判斷設定 Cookie 的位置。 |
| `oi` | 無 | **已不再使用。** 最後一頁的物件執行個體。 用於舊版 Activity Map。 |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | 最後一頁的物件識別碼。 用於目前版本的Activity Map。 |
| `oidt` | 無 | **已不再使用。** 最後一頁的物件識別碼型別。 用於舊版 Activity Map。 |
| `ot` | 無 | **已不再使用。** 最後一頁的物件名稱。 用於舊版 Activity Map。 |
| `p` | 無 | **已不再使用。** 瀏覽器中使用的外掛程式清單。 |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | 用於[[!UICONTROL 頁面]](/help/components/dimensions/page.md)維度。 |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | 用於[[!UICONTROL 找不到頁面]](/help/components/dimensions/pages-not-found.md)維度。 |
| `pccr` | 無 | 永久性Cookie檢查重新導向旗標。 由Adobe資料收集伺服器為新訪客設定，並一律設為`true`。 當新訪客的Cookie支援不明時，資料收集伺服器會將此標幟重新導向影像要求至本身，以確認永久性Cookie檢查已發生。 如果訪客拒絕Cookie，此引數可防止無限重新導向。 |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | 決定點選型別。 有效值包括`lnk_o` （[[!UICONTROL 自訂連結]](/help/components/dimensions/custom-link.md)）、`lnk_d` （[[!UICONTROL 下載連結]](/help/components/dimensions/download-link.md)）、`lnk_e` （[[!UICONTROL 退出連結]](/help/components/dimensions/exit-link.md)）和`tnt` （目標點選的Analytics）。 |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | 發生自訂連結的URL。 |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | [自訂連結](/help/components/dimensions/custom-link.md)的易記名稱。 |
| `pev3` | 無 | **已不再使用。** 追蹤舊版視訊報表中的里程碑。 |
| `pf` | 無 | 平台標幟；僅供 Adobe 使用。 不可變更。 |
| `pid` | 無 | **已不再使用。** 最後一頁的頁面識別碼。 用於舊版 Activity Map。 |
| `pidt` | 無 | **已不再使用。** 最後一頁的頁面識別碼類型。 用於舊版 Activity Map。 |
| `pl` | [`products`](../vars/page-vars/products.md) | `products`引數的簡稱。 |
| `products` | [`products`](../vars/page-vars/products.md) | 產品變數。 用於[[!UICONTROL 產品]](/help/components/dimensions/product.md)和[[!UICONTROL 類別]](/help/components/dimensions/category.md)維度。 |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | 用於[[!UICONTROL 購買ID]](/help/components/dimensions/purchase-id.md)維度。 |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | 點擊的反向連結 URL。 用於流量來源維度，例如[[!UICONTROL 反向連結]](/help/components/dimensions/referrer.md)和[[!UICONTROL 反向連結網域]](/help/components/dimensions/referring-domain.md)。 |
| `s` | 無 | 螢幕解析度，單位為 `width x height`。 用於[[!UICONTROL 螢幕解析度]](/help/components/dimensions/monitor-resolution.md)維度。 |
| `sdid` | 無 | 補充資料ID。 連結描述相同事件的多個點選，例如[Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html)整合中的Analytics和Target點選。 |
| `server` | [`server`](../vars/page-vars/server.md) | 用於[[!UICONTROL 伺服器]](/help/components/dimensions/server.md)維度。 |
| `sv` | [`server`](../vars/page-vars/server.md) | `server`引數的簡稱。 |
| `state` | [`state`](../vars/page-vars/page-variables.md#retired-page-variables) | **已不再使用。** 擷取訪客通常透過送貨或帳單表單進入的美國州。 |
| `t` | 無 | 產生點擊的日期/時間。 在JavaScript中使用格式`dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss`為日期/時間。 `0`月為一月，而`11`月是十二月。<br>- `w`是一週中的某天。 `0`是星期日，而`6`是星期六。<br>- `o`是以分鐘為單位的負GMT時差。 例如，`420` 是 GMT-7。 |
| `tnt` | 無 | 在[Analytics中用於Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t.html)整合的Target資料裝載。 在`pe=tnt`時傳送。 |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | 隨點擊設定的自訂時間戳記。 通常用於離線追蹤。 |
| `u` | 無 | **已不再使用。** 舊版Activity Map中使用的帳戶標籤。 |
| `v` | 無 | 用於 [[!UICONTROL Java 已啟用]](/help/components/dimensions/java-enabled.md)維度。 |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | 用於[[!UICONTROL 追蹤代碼]](/help/components/dimensions/tracking-code.md)維度。 |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md) (或自訂轉換維度)。 |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | 訪客ID覆寫變數。 |
| `vidn` | 無 | 由Adobe資料收集伺服器為新訪客設定，在重新導向的影像要求中附帶`pccr`引數。 包含儲存在訪客Cookie中的訪客ID值。 |
| `vmf` | [`visitorMigrationServer`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **已不再使用。** 從第三方移轉至第一方Cookie期間使用的訪客移轉伺服器。 |
| `vmt` | [`visitorMigrationKey`](../vars/config-vars/configuration-variables.md#retired-configuration-variables) | **已不再使用。** 訪客移轉金鑰，有助於將實作從第三方移轉至第一方Cookie。 |
| `vvp` | 無 | **已不再使用。** Data Connectors中使用的變數提供者。 |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | 與 Data Sources 搭配使用，將線上和離線資料繫結在一起。 |
| `zip` | [`zip`](../vars/page-vars/zip.md) | 用於[郵遞區號](/help/components/dimensions/zip-code.md)維度。 |
